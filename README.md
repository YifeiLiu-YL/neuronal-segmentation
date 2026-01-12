# Neuronal Cell Segmentation (Cellpose-SAM + Cellpose 3)

A practical, end-to-end workflow for **neuronal cell segregation/segmentation** using **Cellpose-SAM as the default**, with **Cellpose 3 as a fallback + training path**.  
Primary goal: **identify all neurons that are recognizable by human manual correction** (coverage/recall-focused).  
Boundary-level precision is **not** the main objective.

---

## What this repo provides

- A step-by-step **segmentation workflow** (human-in-the-loop, reproducible)
- From-scratch usage guides for:
  - **Cellpose-SAM**
  - **Cellpose 3**
- Example inputs/outputs to help you replicate results quickly
- Optional: periodic training loop for Cellpose 3 using manually corrected masks

---

## Workflow overview

**Default approach:** run Cellpose-SAM first.  
**Fallback:** if Cellpose-SAM clearly under-detects neurons, run Cellpose 3 and proceed with manual correction + training.

High-level flow:

1. **Run Cellpose-SAM** on an image
2. **Human check** vs rough visual expectation (qualitative)
3. If **under-detection** is obvious → **run Cellpose 3** on the same image
4. Choose the output with higher **correctness** (coverage of human-identifiable neurons)
5. **Manual correction** (ground truth)
6. **Accumulate corrected masks** → periodically **train Cellpose 3**
7. Iterate to reduce manual correction over time

---

## Quick start

> This section is intentionally minimal. Detailed guides are in `docs/`.

### 1) Install

```bash
pip install -r requirements.txt
