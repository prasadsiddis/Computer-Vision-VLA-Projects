# Waymo Open Dataset Camera-LiDAR VLA

Notebook: `waymo_camera_lidar_vla.ipynb`

## Overview

This project is a Waymo Open Dataset style VLA starter. It combines camera-level scene context with LiDAR-style object density, weather, and range cues, then produces a short driving-language explanation and a high-level action.

The included sample manifest is small so the notebook runs immediately. For real experiments, replace the sample rows with Waymo Open Dataset segment metadata and perception outputs.

## Dataset

Waymo Open Dataset is a large-scale autonomous-driving dataset with synchronized camera and LiDAR data, 2D and 3D boxes, tracking IDs, and diverse driving scenes. The full dataset should be downloaded through the official Waymo Open Dataset portal instead of committed to Git.

## Expected Real Dataset Setup

```text
09-waymo-camera-lidar-vla/
  data/
    waymo/
      training/
      validation/
      testing/
```

Install common tooling:

```bash
pip install waymo-open-dataset-tf-2-12-0 pandas
```

## VLA Mapping

| VLA Part | Waymo Version |
|---|---|
| Vision | camera frames, LiDAR point clouds, 2D and 3D detections |
| Language | scene caption with object counts, weather, visibility, and hazards |
| Action | stop, yield, slow down, change lane, or keep lane |

## Project Workflow

1. Load camera and LiDAR style scene summaries.
2. Build natural-language scene captions.
3. Score risk from object distance, pedestrian/cyclist count, and visibility.
4. Select a high-level action.
5. Explain the decision as a VLA trace.

## Upgrade Path

- Parse real Waymo TFRecord segments.
- Add image thumbnails from front, side, and rear cameras.
- Add point-cloud density and 3D box distance features.
- Train an action classifier from generated VLA labels.
- Compare rule decisions against end-to-end driving model outputs.

## References

- Waymo Open Dataset: https://waymo.com/open/
- Waymo Open Dataset paper: https://arxiv.org/abs/1912.04838
