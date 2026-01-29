# SD4GL
SD4GL: A Sight-Singing Practice Score Dataset for Score Generation with LLMs 🎵

This repository contains supporting materials for our submitted paper. The complete dataset will be released upon paper acceptance.

## Current Content 📁

- `sample_data/`: 100 example standard music scores in ABC notation format 🎼
- `sample_data_tagged/`: Corresponding tagged versions of the sample ABC music scores with labels as described in our paper 🏷️
- `subjective_evaluation/`: Subjective evaluation dataset from A/B blind tests of generated vs. ground-truth scores 📊
  - `paired_data_by_id/`: 300 pairs of notagen-model-generated and ground-truth scores, grouped by `pair_id`. Note that only a subset of these audio pairs is provided currently; the full set will be released upon paper acceptance 🎧
  - `pairs.csv`: Complete metadata for all 300 test pairs, including difficulty levels, mode, and measures. This file serves as the core reference for linking evaluation data to corresponding audio pairs via pair_id 📋

## Difficulty Assessment Criteria 📏
The dataset adopts a three-level difficulty classification system for sight-singing scores, covering **pitch difficulty**, **interval difficulty**, and **rhythm difficulty**. The specific criteria are detailed in the table below.

| Difficulty Type | Difficulty Level | Classification Criteria |
|-----------------|------------------|-------------------------|
| **Pitch Difficulty** | Hard | pitch_range > 18 semitones |
| | Medium | 12 semitones < pitch_range ≤ 18 semitones |
| | Easy | pitch_range ≤ 12 semitones |
| **Interval Difficulty** | Hard | large_leap_ratio ≥ 0.1 |
| | Medium | moderate_leap_ratio ≥ 0.3 |
| | Easy | Otherwise |
| **Rhythm Difficulty** | Hard | triplet_ratio > 0.25 or dotted_note_ratio > 0.2 or syncopation_ratio > 0.1 |
| | Medium | triplet_ratio > 0.1 or dotted_note_ratio > 0.08 or syncopation_ratio > 0.05 |
| | Easy | Otherwise |

### Notes
1. **pitch_range**: The number of semitones between the highest and lowest notes in the score.
2. **Interval-related definitions**: Large leaps refer to intervals $\ge 7$ semitones (perfect fifth and above); moderate leaps refer to intervals of 3–6 semitones (minor third to diminished fifth).
3. **Ratio calculation**: Interval ratio is the proportion of the corresponding interval type to the total number of intervals in the score; rhythm pattern ratio is the ratio of the total duration of notes in the corresponding rhythm type to the total duration of the score.
4. **Rhythm criteria supplement**: "Otherwise" for rhythm difficulty means no significant presence of complex rhythmic patterns (dotted rhythms, triplets, syncopation).
