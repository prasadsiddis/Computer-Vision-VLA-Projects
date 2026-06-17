# Project Roadmap

## Phase 1: Baseline Portfolio

- Keep each notebook runnable with small sample manifests.
- Maintain clear README files for every project.
- Include visual outputs and summary results at the repository level.
- Track assumptions and dataset limitations explicitly.

## Phase 2: Real Dataset Integration

- Run nuScenes mini through the scene-caption-to-action workflow.
- Add BDD100K image attributes and detection labels.
- Generate CARLA traces with camera, segmentation, route command, and control logs.
- Add KITTI calibration and stereo/depth loading.
- Add Argoverse 2 map and actor-forecast features.

## Phase 3: Model Upgrades

- Replace rule-based captions with a vision-language model.
- Train an action classifier from structured perception features.
- Compare rule policies, classical ML baselines, and VLM/VLA-style policies.
- Add failure-case review tables for unsafe or ambiguous scenes.

## Phase 4: Research-Ready Presentation

- Add notebook screenshots and selected output panels.
- Add reproducible experiment configs.
- Track metrics by dataset, weather, lighting, and vulnerable road-user presence.
- Prepare a short research write-up connecting the projects to autonomous-driving VLA work.
