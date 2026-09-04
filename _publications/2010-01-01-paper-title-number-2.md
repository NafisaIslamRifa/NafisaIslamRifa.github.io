---

title: "Visual Grounding and Explainability for Prompt-Driven Radiology Report Generation"
collection: publications
category: manuscripts
permalink: /publication/2026-09-04-visual-grounding-radiology-report-generation
excerpt: "This paper presents a parameter-efficient multimodal framework for radiology report generation with visual grounding. The approach combines a frozen Rad-DINO vision encoder, a lightweight spatial adapter, and a parameter-efficient Qwen2.5-3B language model to generate radiology reports and, when prompted, corresponding localisation coordinates."
date: 2026-09-04
venue: 'Accepted for publication and presentation at the 7th International Conference on Medical Imaging and Computer-Aided Diagnosis (MICAD 2026).'
paperurl: ''
bibtexurl: ''
citation: '@INPROCEEDINGS{micad2026_708,
title = {Visual Grounding and Explainability for Prompt-Driven Radiology Report Generation},
author = {Nafisa Islam Rifa},
booktitle = {7th International Conference on Medical Imaging and Computer-Aided Diagnosis (MICAD 2026)},
year = {2026},
note = {Paper ID: 708}
}'
--

Radiology report generation systems aim to automatically produce clinically relevant descriptions from chest X-ray images, but generating text alone does not necessarily demonstrate that the model is using image-specific evidence. This work investigates whether generated radiology reports and valid visual grounding can provide evidence of image-conditioned reasoning.

The proposed framework combines a frozen Rad-DINO vision encoder with a lightweight spatial adapter and a parameter-efficient Qwen2.5-3B language model. The language model is adapted using low-rank adaptation (LoRA), while the spatial adapter projects visual features into the language model's representation space while preserving spatial information. The system supports two prompt-driven modes: report generation and report generation with localisation.

The study evaluates the framework from two complementary perspectives: natural language report generation and visual localisation. Report quality is assessed using standard text-generation metrics, while grounding performance is evaluated using localisation metrics including mean Intersection over Union (mIoU), IoU-based measures, and Mass-in-Box. Attribution-based methods such as Grad-CAM, HiRes-CAM, and Score-CAM, together with non-learned spatial baselines, are also considered for comparison.

The results highlight an important distinction between syntactically valid grounding and accurate visual localisation. Although the model can generate reports together with valid coordinate representations, localisation quality remains challenging, demonstrating that the presence of grounding tokens alone should not be interpreted as evidence of reliable image-specific reasoning.

## This research provides an efficient framework for auditing visual grounding and explainability in prompt-driven radiology report generation while requiring only a small fraction of the underlying language model parameters to be trained.

Acceptance: MICAD 2026, Paper ID 708. Accepted for publication and presentation, October 22–24, 2026.
