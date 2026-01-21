# SD4GL
SD4GL: A Sight-Singing Scores Dataset for Score Generation with LLM 🎵

This repository contains supporting materials for our submitted paper. The complete dataset will be released upon paper acceptance.

## Current Content 📁

- `sample_data/`: 100 example standard music scores in ABC notation format 🎼
- `sample_data_tagged/`: Corresponding tagged versions of the sample ABC music scores with labels as described in our paper 🏷️
- `subjective_evaluation/`: Subjective evaluation dataset from A/B blind tests of generated vs. ground-truth scores 📊
  - `paired_data_by_id/`: 300 pairs of notagen-model-generated and ground-truth scores, grouped by `pair_id`. Note that only a subset of these audio pairs is provided currently; the full set will be released upon paper acceptance 🎧
  - `pairs.csv`: Complete metadata for all 300 test pairs, including difficulty levels, mode, and measures. This file serves as the core reference for linking evaluation data to corresponding audio pairs via pair_id 📋
