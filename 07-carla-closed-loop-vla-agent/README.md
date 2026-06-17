# CARLA Closed-Loop VLA Agent

Notebook: `carla_closed_loop_vla_agent.ipynb`

## Overview

This project prepares a CARLA-based Vision-Language-Action driving agent. CARLA is an open-source simulator for autonomous-driving research and supports camera, lidar, radar, depth, semantic segmentation, maps, traffic actors, weather, and closed-loop control.

The included notebook uses sample observations when CARLA is not installed, then shows how the same policy can connect to CARLA sensor data.

## Dataset / Simulator

CARLA is a simulator rather than a static dataset. You can generate your own dataset by recording synchronized:

- RGB camera images
- semantic segmentation
- vehicle speed
- route command
- nearby actors
- chosen control action

## Expected Real Setup

Install CARLA locally and run the simulator server. Keep generated data outside Git:

```text
07-carla-closed-loop-vla-agent/
  data/
    carla_runs/
      run_001/
        images/
        segmentation/
        controls.csv
```

## VLA Mapping

| VLA Part | CARLA Version |
|---|---|
| Vision | RGB camera, depth, semantic segmentation |
| Language | route instruction such as "turn left at the next intersection" |
| Action | throttle, brake, steer, or high-level policy action |

## Project Workflow

1. Define a route instruction.
2. Read simulator observations.
3. Convert observations into a scene state.
4. Apply a safety-aware VLA policy.
5. Output high-level action or low-level control.
6. Optionally record frames and controls as a dataset.

## References

- CARLA official site: https://carla.org/
- CARLA documentation: https://carla.readthedocs.io/
