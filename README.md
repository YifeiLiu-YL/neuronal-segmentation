# Neuronal Cell Segmentation Workflow

## Motivation

This repository provides a practical workflow for neuronal cell segmentation
using Cellpose-SAM and Cellpose 3 with human-in-the-loop iteration.

The primary goal is to identify all neurons that are recognizable by human
manual correction, with iterative training to reduce manual effort over time.
This workflow prioritizes neuron identification (coverage / recall) rather than
precise boundary alignment.


## What This Repo Provides

This repository provides:

- A step-by-step workflow for neuronal cell segregation
- Guidance on using Cellpose-SAM and Cellpose 3 from scratch
- A comparison-based strategy to select between models
- A manual correction and training loop for Cellpose 3
- Example scripts and example runs for reproducibility

The repository is designed so that a user without prior experience with
Cellpose-SAM or Cellpose 3 can follow the workflow and perform neuronal
segmentation.


## Workflow Overview

The workflow consists of the following stages:

1. Run Cellpose-SAM as the default segmentation method
2. Compare the output with qualitative human expectation
3. Apply Cellpose 3 when Cellpose-SAM under-detects neurons
4. Select the output that best matches human-identifiable neurons
5. Perform manual correction on the selected output
6. Accumulate corrected masks as training data
7. Periodically train Cellpose 3 to reduce future under-detection

Detailed descriptions of each step are provided [here](https://github.com/YifeiLiu-YL/neuronal-segmentation/blob/main/Segmentation%20Workflow.md).


## Examples

An example dataset is provided [here](https://drive.google.com/drive/folders/17Qsv3mLei5XZf_g6K7UqtO_a4qKljpi7?usp=drive_link)

The dataset consists of a single-plane, single-channel neuronal recording.
It is intended to demonstrate the segmentation workflow and to serve as a
reference for running Cellpose-SAM, Cellpose 3, and manual correction.


## FAQ

See FAQs [here](https://github.com/YifeiLiu-YL/neuronal-segmentation/blob/main/FAQ.md).
