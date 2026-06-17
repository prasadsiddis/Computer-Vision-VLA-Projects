# Dataset Setup for Real Autonomous-Driving Projects

This branch includes small sample manifests so notebooks run without large downloads. To run the projects on real data, download each dataset from its official source and keep the full data outside Git.

## Recommended Order

If you want to run real-data experiments, start small:

1. KITTI: easiest classic computer vision benchmark to inspect locally.
2. BDD100K: useful for image-level multitask driving labels.
3. Talk2CarSlim: useful for command grounding without the full nuScenes setup.
4. nuScenes mini: best next step for multimodal autonomous-driving scenes.
5. CARLA: useful when you want generated closed-loop driving traces.
6. Argoverse 2 or Waymo Open Dataset: stronger research-scale options, but heavier to manage.

## Why Full Datasets Are Not Committed

- nuScenes full data can require hundreds of GB.
- BDD100K includes large image and video archives.
- CARLA is a simulator with large binaries and generated recordings.
- Talk2Car can be used in a slim form, but the full setup may depend on nuScenes.
- Waymo Open Dataset, Argoverse 2, and KITTI contain large sensor archives that should be downloaded from their official sources.
- Dataset licenses and terms should be accepted directly from the dataset owners.

## Recommended Local Layout

```text
data_local/
  nuscenes/
  bdd100k/
  carla_runs/
  talk2car/
  waymo/
  argoverse2/
  kitti/
```

Keep `data_local/` ignored by Git.

## How to Connect Real Data to the Notebooks

Each notebook starts from a small `sample_*` manifest. For real experiments, build the same columns from the official dataset files, then reuse the notebook's captioning and action-policy functions as a baseline.

This keeps the repo clean while still making each project easy to upgrade.

## Sources

- nuScenes: https://www.nuscenes.org/nuscenes
- nuScenes devkit: https://github.com/nutonomy/nuscenes-devkit
- BDD100K toolkit: https://github.com/bdd100k/bdd100k
- CARLA: https://carla.org/
- Talk2Car: https://github.com/talk2car/Talk2Car
- Waymo Open Dataset: https://waymo.com/open/
- Argoverse 2: https://www.argoverse.org/av2.html
- KITTI: https://www.cvlibs.net/datasets/kitti/
