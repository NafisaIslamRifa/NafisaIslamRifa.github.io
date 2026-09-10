---
title: "Visual Grounding and Explainability for Prompt-Driven Radiology Report Generation"
collection: publications
category: manuscripts
permalink: /publication/2026-09-04-visual-grounding-radiology-report-generation
excerpt: "This paper presents a parameter-efficient multimodal framework for radiology report generation with visual grounding. The approach combines a frozen Rad-DINO vision encoder, a lightweight spatial adapter, and a parameter-efficient Qwen2.5-3B language model to generate radiology reports and, when prompted, corresponding localisation coordinates."
date: 2026-09-04
venue: 'Accepted for publication and presentation at 7th International Conference on Medical Imaging and Computer-Aided Diagnosis (MICAD 2026).'
paperurl: 'https://drive.google.com/file/d/1IQNNWdiXM0mmZVe9uwBSnbmuaUKDNe4s/view?usp=sharing'
bibtexurl: ''
citation: '@INPROCEEDINGS{micad2026_708,
title = {Visual Grounding and Explainability for Prompt-Driven Radiology Report Generation},
author = {Nafisa Islam Rifa},
booktitle = {7th International Conference on Medical Imaging and Computer-Aided Diagnosis (MICAD 2026)},
year = {2026},
note = {Paper ID: 708}
}'
---

Radiology report generation systems aim to automatically produce clinical descriptions from medical images. However, generating a report alone does not necessarily demonstrate whether the model is using image-specific visual evidence. To address this issue, this work investigates visual grounding and explainability in prompt-driven radiology report generation.

The proposed framework combines a frozen vision encoder with a lightweight spatial adapter and a parameter-efficient language model. The model supports two prompt-driven modes: report generation and report generation with visual localisation, allowing the system to generate radiology reports together with corresponding spatial coordinates when localisation is requested.

The model is evaluated from two complementary perspectives: the quality of generated radiology reports and the accuracy of visual grounding. Report generation is assessed using standard natural language generation metrics, while localisation performance is evaluated using overlap-based metrics and comparisons with attribution-based and non-learned visual grounding baselines.

Experimental results demonstrate that the proposed framework can generate radiology reports while also producing syntactically valid visual grounding outputs. However, the results also highlight an important distinction between valid grounding representations and accurate localisation, showing that the presence of grounding coordinates alone does not necessarily provide evidence of reliable image-specific reasoning.

This research demonstrates a parameter-efficient approach for investigating visual grounding and explainability in radiology report generation, with potential applications in developing more transparent and auditable medical vision-language systems.




















