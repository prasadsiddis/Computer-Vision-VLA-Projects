# KITTI Stereo 3D Driving Perception

Notebook: `kitti_stereo_3d_driving_perception.ipynb`

## Overview

This project is a KITTI-style perception starter for autonomous driving. It converts stereo/depth and 3D detection cues into a compact driving scene description and a high-level action.

The included sample manifest lets the notebook run immediately. For real experiments, use KITTI raw, object detection, stereo, or depth benchmark data.

## Dataset

KITTI is a classic autonomous-driving computer vision benchmark with stereo images, optical flow, visual odometry, object detection, tracking, and 3D perception tasks. It is smaller than modern fleet-scale datasets but remains useful for clean perception baselines.

## Expected Real Dataset Setup

```text
11-kitti-stereo-3d-driving-perception/
  data/
    kitti/
      image_2/
      image_3/
      velodyne/
      label_2/
      calib/
```

Install common tooling:

```bash
pip install pandas numpy opencv-python
```

## VLA Mapping

| VLA Part | KITTI Version |
|---|---|
| Vision | stereo image pair, depth estimate, 2D/3D boxes |
| Language | scene description with depth, object class, and occlusion evidence |
| Action | stop, slow down, keep lane, or prepare lane change |

## Project Workflow

1. Load a KITTI-style frame summary.
2. Convert depth and object cues into a caption.
3. Estimate collision risk from near objects and occlusion.
4. Produce a high-level driving action.
5. Explain the result as a VLA decision trace.

## Upgrade Path

- Add real KITTI image and calibration loading.
- Estimate disparity from stereo images.
- Parse `label_2` files for object class and 3D box position.
- Train a simple depth-aware action classifier.
- Compare rule actions with learned perception embeddings.

## References

- KITTI Vision Benchmark Suite: https://www.cvlibs.net/datasets/kitti/
- KITTI paper: https://ieeexplore.ieee.org/document/6248074
