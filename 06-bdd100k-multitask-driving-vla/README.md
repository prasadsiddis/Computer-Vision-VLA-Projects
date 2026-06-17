# BDD100K Multi-Task Driving VLA

Notebook: `bdd100k_multitask_driving_vla.ipynb`

## Overview

This project uses BDD100K-style image attributes and object labels to produce driving-scene captions and high-level actions. BDD100K is well suited for VLA autonomous-driving work because it contains diverse road scenes with weather, time of day, scene type, detection, lane, drivable-area, and segmentation tasks.

## Dataset

The full BDD100K dataset is large and must be downloaded from the official dataset source. This project includes a small sample label file that mimics useful BDD100K fields so the notebook can run immediately.

## Expected Real Dataset Setup

```text
06-bdd100k-multitask-driving-vla/
  data/
    bdd100k/
      images/100k/train/
      images/100k/val/
      labels/
```

## VLA Mapping

| VLA Part | BDD100K Version |
|---|---|
| Vision | weather, time of day, scene, object counts, lane/drivable cues |
| Language | generated scene caption and question-answer style explanation |
| Action | stop, yield, slow down, keep lane, or proceed |

## Project Workflow

1. Load BDD100K-style sample labels.
2. Generate driving-scene captions.
3. Estimate risk from pedestrians, vehicles, traffic lights, and weather.
4. Predict a high-level action.
5. Prepare the same schema for full BDD100K labels.

## References

- BDD100K paper: https://arxiv.org/abs/1805.04687
- BDD100K toolkit: https://github.com/bdd100k/bdd100k
