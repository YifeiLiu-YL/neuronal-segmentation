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
