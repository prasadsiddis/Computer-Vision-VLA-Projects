# Research Notes

## Motivation

Vision-Language-Action models are a promising direction for autonomous driving because they connect scene perception, natural-language reasoning, and decision making. This portfolio is structured around that connection rather than around isolated perception tasks.

The core question is:

> How can visual driving-scene evidence be converted into grounded language explanations and safe high-level driving actions?

## Working Hypothesis

A useful VLA driving system needs three inspectable layers:

1. **Perception layer:** camera, LiDAR, stereo, segmentation, map, and object cues.
2. **Language layer:** captions, commands, explanations, questions, and reasoning traces.
3. **Action layer:** stop, yield, slow down, keep lane, turn, pull over, or prepare a maneuver.

The notebooks start with small tabular manifests so the pipeline is transparent before adding heavier models and datasets.

## Dataset Strategy

The project intentionally covers several autonomous-driving dataset styles:

- **nuScenes:** multimodal scenes with camera, LiDAR, radar, maps, and annotations.
- **BDD100K:** image-level driving attributes and multi-task labels.
- **CARLA:** controllable simulator traces and closed-loop behavior.
- **Talk2Car:** language commands grounded in driving scenes.
- **Waymo Open Dataset:** large-scale camera and LiDAR perception.
- **Argoverse 2:** HD maps and motion forecasting.
- **KITTI:** classic stereo, depth, and 3D perception.

## Current Limitations

- Current notebooks use sample manifests, not full official datasets.
- Action policies are transparent rule baselines, not learned VLA policies.
- The figures are repository-level outputs, not yet full benchmark results.
- No image panels or qualitative examples from official datasets are included yet.

## Near-Term Research Direction

- Add adapters that transform real dataset annotations into each notebook schema.
- Add image thumbnails and scene panels for qualitative analysis.
- Replace rule-based captions with VLM-generated captions.
- Compare rule baselines against learned action classifiers.
- Track failure cases where the model should defer, slow down, or request more context.
