# Dataset Adapter Notes

These notes define how the sample manifests can be replaced with official autonomous-driving datasets.

## Adapter Contract

Each adapter should produce a tabular manifest with:

- a stable sample identifier
- driving-scene context fields
- perception-derived risk features
- a language-ready scene summary
- an expected or annotated high-level action when available

The notebooks should not depend directly on raw dataset file formats. Instead, each raw dataset should be converted into the notebook schema first.

## nuScenes Mini Adapter

Target project: `05-nuscenes-vla-scene-caption-action`

Adapter steps:

1. Load `v1.0-mini` with the nuScenes devkit.
2. Iterate through sample records and select front-camera samples.
3. Count nearby annotated objects by category.
4. Attach ego speed, weather/time metadata when available, and map context.
5. Export rows with the same columns as `sample_nuscenes_scenes.csv`.

## CARLA Trace Adapter

Target project: `07-carla-closed-loop-vla-agent`

Adapter steps:

1. Record RGB camera frames, semantic segmentation frames, speed, traffic-light state, and route command.
2. Add distance-to-pedestrian and distance-to-vehicle estimates.
3. Save one row per simulator step.
4. Keep image files outside Git and store only relative paths in the manifest.

## KITTI Adapter

Target project: `11-kitti-stereo-3d-driving-perception`

Adapter steps:

1. Load calibration files, stereo image pairs, and `label_2` annotations.
2. Estimate nearest vehicle and pedestrian distance from labels or projected LiDAR.
3. Add occlusion and lane-visibility fields.
4. Export the final manifest for depth-aware action-policy experiments.

## Validation Checklist

- Confirm required columns are present.
- Confirm no raw dataset archives are committed.
- Save generated manifests under ignored local data folders unless they are tiny examples.
- Add one qualitative example image panel per dataset when licensing allows it.
