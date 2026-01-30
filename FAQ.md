# FAQ

This section addresses common issues encountered when using Cellpose
for neuronal segmentation, especially on macOS and in training-based workflows.


## Q1. Who is this workflow intended for?

This workflow is designed for:
- Users with little or no prior experience in Cellpose
- Neuronal imaging datasets requiring human-in-the-loop correction
- Labs that need a reproducible and teachable segmentation pipeline
- No prior machine learning background is required.


## Q2. When should I use Cellpose-SAM vs Cellpose 3 training?

This workflow follows a hybrid strategy:
- Use Cellpose-SAM first for automatic segmentation
- If SAM detects too few neurons or produces low-correctness results, switch to Cellpose 3 (training-based) segmentation with manual correction

Cellpose 3 training is recommended when:
- Neuronal morphology is complex
- SAM fails to generalize to the dataset
- Human-corrected annotations are available

## Q3. I cannot delete a selected ROI using the Delete key. Why?

On macOS, keyboard shortcuts for deleting ROIs in Cellpose are not always
reliable due to GUI focus and key-mapping differences.

**Recommended solution:**
- Restart cellpose
- Use `click-select` in `Drawing` to remove it

This method is stable across platforms and Cellpose versions.


## Q4. How do I select ROIs on macOS vs Windows?

- **macOS:** `Command (⌘) + click` to select an ROI
- **Windows:** `Ctrl + click` to select an ROI

Multiple ROIs can be selected by dragging a selection box.


## Q5. My segmentation boundaries are not perfectly aligned. Is this a problem?

For neuronal identification tasks, exact boundary alignment is not required.

The goal of this workflow is:
- Accurate neuron identification
- Consistent labeling for downstream analysis

Minor boundary inaccuracies are acceptable as long as neuron identity is correct.



## Q6. What is the `gradXY` view and do I need to use it?

The `gradXY` view visualizes the internal flow field predicted by Cellpose,
which is used to guide pixels toward cell centers during segmentation.

This view is primarily intended for **model debugging**.
It is **not required** for routine segmentation or manual correction.

Most users can safely ignore this view.


## Q7. I installed Cellpose, but `cellpose.__version__` does not exist. Is my installation broken?

Not necessarily. Some Cellpose versions do not expose the version number
as `cellpose.__version__`.

To reliably check the installed Cellpose version, use:

```bash
python -c "import importlib.metadata as m; print(m.version('cellpose'))"

