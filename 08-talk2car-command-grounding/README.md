# Talk2Car Command Grounding

Notebook: `talk2car_command_grounding.ipynb`

## Overview

This project uses Talk2Car-style command grounding for autonomous driving. Talk2Car contains natural-language commands written for self-driving car scenes, where the model must ground the command to a referred object or region.

The included sample commands let the notebook run immediately. For full experiments, use Talk2CarSlim or Talk2Car with nuScenes as described by the official repository.

## Dataset

Talk2Car is built on top of nuScenes and includes commands such as parking instructions or object references. The official repository also provides a slimmer setup that can be used without downloading the full nuScenes dataset.

## Expected Real Dataset Setup

```text
08-talk2car-command-grounding/
  data/
    talk2car/
      commands/
      images/
```

## VLA Mapping

| VLA Part | Talk2Car Version |
|---|---|
| Vision | scene image and candidate object boxes |
| Language | passenger command |
| Action | grounded target plus action intent |

## Project Workflow

1. Load sample commands and candidate objects.
2. Parse action intent from language.
3. Score object candidates using keyword grounding.
4. Select a referred object.
5. Convert the grounded command into a high-level action.

## References

- Talk2Car official repo: https://github.com/talk2car/Talk2Car
- Talk2Car paper: https://arxiv.org/abs/1909.10838
