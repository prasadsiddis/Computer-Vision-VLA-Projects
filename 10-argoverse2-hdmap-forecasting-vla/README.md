# Argoverse 2 HD Map Forecasting VLA

Notebook: `argoverse2_hdmap_forecasting_vla.ipynb`

## Overview

This project is an Argoverse 2 style VLA starter focused on map-aware forecasting. It uses lane topology, actor motion, crosswalk proximity, and route intent to produce an explanation and a safe high-level action.

The included sample manifest runs without the full dataset. Replace it with Argoverse 2 sensor or motion-forecasting data for a real experiment.

## Dataset

Argoverse 2 includes sensor data, large-scale LiDAR sequences, motion-forecasting scenarios, and scenario-level HD maps. It is especially useful for autonomous-driving projects that connect perception, maps, and future actor motion.

## Expected Real Dataset Setup

```text
10-argoverse2-hdmap-forecasting-vla/
  data/
    argoverse2/
      sensor/
      motion_forecasting/
      maps/
```

Install common tooling:

```bash
pip install av2 pandas
```

## VLA Mapping

| VLA Part | Argoverse 2 Version |
|---|---|
| Vision | sensor detections and tracked actor states |
| Language | route-aware explanation of lane, crosswalk, and future motion |
| Action | yield, slow down, turn, keep lane, or stop |

## Project Workflow

1. Load a compact scenario table.
2. Convert map and actor features into a language scene summary.
3. Estimate conflict risk from forecasted actor paths.
4. Select a high-level driving action.
5. Explain the action using lane and map evidence.

## Upgrade Path

- Use official motion-forecasting parquet files.
- Query local HD map lane and crosswalk geometry.
- Add future trajectory error metrics.
- Train a map-aware action policy.
- Generate VLA instruction-response pairs from scenario context.

## References

- Argoverse 2: https://www.argoverse.org/av2.html
- Argoverse 2 paper: https://arxiv.org/abs/2301.00493
