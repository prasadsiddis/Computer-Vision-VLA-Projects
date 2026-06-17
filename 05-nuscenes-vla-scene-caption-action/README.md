# nuScenes VLA Scene Caption to Action

Notebook: `nuscenes_vla_scene_caption_action.ipynb`

## Overview

This project is a nuScenes-style Vision-Language-Action starter. It turns multimodal autonomous-driving scene metadata into a short scene caption and a high-level driving action.

The included sample manifest lets the notebook run immediately. For real experiments, replace the sample rows with nuScenes mini or full dataset metadata using the nuScenes devkit.

## Dataset

nuScenes is a multimodal autonomous-driving dataset with camera, lidar, radar, GPS/IMU, maps, and annotations. The full dataset is large, so this project includes only a tiny sample manifest that follows the kind of fields needed by a VLA pipeline.

## Expected Real Dataset Setup

Place nuScenes data outside Git or under a local ignored directory:

```text
05-nuscenes-vla-scene-caption-action/
  data/
    nuscenes/
      v1.0-mini/
      samples/
      sweeps/
      maps/
```

Install the devkit:

```bash
pip install nuscenes-devkit
```

## VLA Mapping

| VLA Part | nuScenes Version |
|---|---|
| Vision | camera frame plus 3D scene annotations |
| Language | generated caption describing traffic light, objects, and risk |
| Action | stop, yield, slow down, keep lane, or proceed |

## Project Workflow

1. Load sample scene metadata.
2. Generate a compact language caption from scene attributes.
3. Score driving risk.
4. Select a high-level driving action.
5. Explain the action with scene evidence.

## Upgrade Path

- Use nuScenes mini for real camera samples.
- Add object counts from nuScenes annotations.
- Add map and ego-pose features.
- Replace rule-based captions with a VLM.
- Train an action classifier from annotated driving decisions.

## References

- nuScenes dataset: https://www.nuscenes.org/nuscenes
- nuScenes devkit: https://github.com/nutonomy/nuscenes-devkit
