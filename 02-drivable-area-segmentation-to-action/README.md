# Drivable-Area Segmentation to Action

Notebook: `drivable_area_segmentation_to_action.ipynb`

## Overview

This project connects computer vision segmentation to autonomous-driving action decisions. It simulates a segmentation output with drivable area, lane center, and obstacle location, then converts those perception signals into high-level driving actions.

## Problem Statement

Given a segmentation-style perception output, decide whether the vehicle should:

- stop
- slow down
- steer left
- steer right
- keep lane

## VLA Mapping

| VLA Part | This Project |
|---|---|
| Vision | Synthetic segmentation mask and obstacle map |
| Language | Action explanation in natural language |
| Action | Driving policy derived from segmentation features |

## Workflow

1. Generate synthetic road masks.
2. Estimate drivable area coverage.
3. Estimate lane offset from center.
4. Detect obstacles in the ego vehicle path.
5. Recommend a high-level action.
6. Visualize the scene and decision.

## Skills Demonstrated

- Semantic-segmentation reasoning
- Drivable-area estimation
- Obstacle-aware action policy
- Explainable autonomous-driving decisions
- Perception-to-planning interface design

## How To Improve

- Replace synthetic masks with segmentation model predictions.
- Use real road datasets such as BDD100K, Cityscapes, or nuScenes.
- Add temporal smoothing across video frames.
- Add uncertainty estimates for ambiguous segmentation regions.
- Connect the output to a trajectory planner.
