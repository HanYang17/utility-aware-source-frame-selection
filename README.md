# Downstream-Utility-Aware Source-Frame Selection

This research release contains the selector implementation, configuration,
trained checkpoint, manuscript, and illustrative figures for reference-based
video color grading.

## Contents

- `code/`: feature extraction, model, training, inference, protocol checks, and deterministic tests.
- `config/selector_config.json`: configuration bound to the released checkpoint.
- `weights/selector_checkpoint.pt`: trained selector checkpoint.
- `main.pdf`: revised manuscript.
- `figures/`: motivation and matched qualitative comparison figures.
- `site/`: static project-page files suitable for GitHub Pages.

Benchmark videos, target ground truth, target LUTs, third-party encoder weights,
and renderer implementations are not redistributed. They remain subject to
their original dataset and software terms.

## Method

The selector receives a target reference and a candidate set. It combines
semantic correspondence, correspondence-guided local color evidence, and
set-aware utility ranking, then returns one source frame to an unchanged
grading backend. Utility labels are generated offline during training and are
not inputs at inference.

## Principal result

On the 100-case benchmark, the complete system reaches **27.43 dB PSNR**;
VCG reports **24.55 dB**, an arithmetic difference of **+2.88 dB**. LPIPS and
CIEDE2000 are reported as complementary controlled evidence in the manuscript.
