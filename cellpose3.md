# Cellpose 3 Workflow

This document describes how to use Cellpose 3 within the neuronal cell
segmentation workflow of this repository.

Cellpose 3 is used when Cellpose-SAM under-detects neurons and when supervised
training is required to recover neurons identifiable by human inspection.

---

## 1. Environment Setup and Launch

This section ensures that Cellpose 3 is correctly installed and that the GUI
can be launched successfully. Once the GUI opens properly, you are ready to
begin segmentation.

### Create and Activate Environment

It is recommended to use a dedicated conda environment for Cellpose 3.

```bash
conda create -n cellpose3 python=3.10 -y
conda activate cellpose3
```
### Install Cellpose with GUI Support

Install Cellpose including the graphical user interface:

```bash
python -m pip install 'cellpose[gui]'
```
If GPU acceleration is desired, make sure the appropriate CUDA-compatible
PyTorch version is installed on your system.

### Launch the Cellpose GUI

Start the Cellpose graphical interface with:

```bash
python -m cellpose
```
A window should open displaying the Cellpose GUI.

<!-- Screenshot 1: Cellpose GUI main window immediately after launch, before loading any images. This screenshot confirms that the installation and launch were successful. -->

At this stage:

No images need to be loaded

No parameters need to be adjusted

No models need to be selected


The purpose of this step is only to verify that Cellpose 3 is installed and
running correctly.
Once the GUI is open, proceed to loading data and basic visualization.

## 2. Load Data and Basic Visualization

This section covers how to load image data into the Cellpose GUI and how to
navigate the basic visualization modes. The goal is to become familiar with
the interface before running segmentation.

At this stage, it is not necessary to fully understand all views or settings.

---

### Load Image Data

Cellpose supports loading a single image or a folder of images.

To load data:
1. Open the Cellpose GUI
2. Click `File` → `Load image` to load a single image  
   or  
   Click `File` → `Load folder` to load multiple images

Supported image formats include common microscopy formats such as `.tif` and
`.tiff`.

If a folder is loaded, images can be navigated using the left and right arrow
keys on the keyboard. Make sure the image display area is selected before
using the arrow keys.

<!-- Screenshot 2:
File menu showing "Load image" and "Load folder" options.
-->

<!-- Screenshot 3:
Cellpose GUI with a neuronal image successfully loaded.
-->

---

### Image Display Modes

Cellpose provides several visualization modes that can be toggled in the GUI.
Only a subset of these views is relevant for this workflow.

Commonly used views include:

- `image`  
  Displays the original image as loaded.

- `cellprob`  
  Displays the probability map indicating how likely each pixel is to be
  inside a cell. Brighter regions indicate higher confidence.

- `gradXY`  
  Displays the flow field used internally by Cellpose. This view is not
  required for routine use and can generally be ignored.

At this stage, it is sufficient to focus on:
- `image` to inspect the raw data
- `cellprob` to gain intuition about which regions the model considers cell-like

<!-- Screenshot 4:
Side-by-side or toggled view showing "image" and "cellprob".
-->

---

### Notes

- Do not adjust segmentation parameters at this stage
- Do not attempt to interpret the flow field in detail
- The purpose of this step is familiarity with the GUI and visualization only

Once the image is loaded and visible, proceed to running segmentation.
