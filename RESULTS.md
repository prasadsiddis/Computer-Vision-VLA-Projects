# Results Summary

This repository uses small sample manifests so the notebooks run quickly while preserving the structure of real autonomous-driving research workflows.

## Current Baseline Outputs

| Area | Current Output | Purpose |
|---|---|---|
| Dataset coverage | `figures/dataset_coverage.png` | Shows the spread across synthetic VLA, segmentation, VQA, nuScenes, BDD100K, CARLA, Talk2Car, Waymo, Argoverse 2, and KITTI |
| VLA workflow | `figures/vla_pipeline_workflow.png` | Summarizes the vision-to-language-to-action pipeline |
| Risk scoring | `figures/sample_risk_scores.png` | Compares simple risk proxies from included sample manifests |
| Notebook traces | `outputs/vla_decision_trace.csv` when notebooks are run | Stores per-sample scene summaries, predicted actions, and evaluation columns |

## Evaluation Approach

The current notebooks use transparent rule-based baselines. This is intentional: the goal is to make the reasoning path inspectable before replacing the policy with learned VLM/VLA components.

The baseline evaluation checks:

- whether the predicted action matches the sample expected action
- which scene features influenced the action
- whether risk scores align with visible scene constraints
- where the rule policy fails and should be replaced by learned models

## Next Research Evaluation Targets

- Run the same notebooks on nuScenes mini, BDD100K images, and CARLA-generated traces.
- Add image panels beside each decision trace.
- Replace rule policies with a VLM captioner plus action classifier.
- Track metrics across dataset, weather, time of day, vulnerable road users, and map context.
