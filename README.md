# Neuronal Cell Segmentation Protocol

This repository provides a reproducible segmentation workflow
for neuronal cells using Cellpose-SAM as the default model,
with Cellpose 3 manual training as a fallback strategy.

## Motivation
Neuronal cells exhibit complex morphologies that are often
challenging for a single segmentation model.
We observed that Cellpose-SAM performs robustly without training
but fails systematically on specific phenotypes.
To address this, we developed a hybrid protocol combining:
- zero-shot segmentation (Cellpose-SAM)
- phenotype-specific supervised training (Cellpose 3)

## Workflow Overview
1. Segment images using Cellpose-SAM
2. Perform quality control (QC)
3. Apply Cellpose 3 only to SAM-failure cases
4. Log model usage and segmentation decisions

See `protocol/overview.md` for details.

## Intended Use
- Neuronal soma / whole-cell segmentation
- Fluorescence microscopy images
- Reproducible and extensible lab workflows
