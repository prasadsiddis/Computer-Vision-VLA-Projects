# Language-Guided Scene to Action

Notebook: `language_guided_scene_to_action.ipynb`

## Overview

This project demonstrates the core idea behind a Vision-Language-Action autonomous-driving system: combine visual scene understanding with a natural-language instruction, then output a high-level driving action.

Instead of using a heavy vision-language model, the notebook uses synthetic perception features and a transparent rule-based planner. This makes the logic easy to inspect and gives a clean foundation for replacing synthetic perception with real model outputs later.

## Problem Statement

Given:

- visual scene cues such as traffic light state, pedestrians, obstacles, lane condition, and distance to intersection
- a natural-language driving command such as "turn left when safe" or "continue through the intersection"

Predict:

- a high-level driving action: `stop`, `yield`, `slow_down`, `keep_lane`, `turn_left`, or `turn_right`
- a short natural-language explanation

## VLA Mapping

| VLA Part | This Project |
|---|---|
| Vision | Structured scene cues representing perception output |
| Language | Driver command or navigation instruction |
| Action | Rule-based driving decision and explanation |

## Workflow

1. Create synthetic driving scenes.
2. Parse natural-language commands into driving intent.
3. Score safety constraints such as pedestrians, red lights, and obstacles.
4. Produce an action recommendation.
5. Generate a human-readable explanation for the decision.

## Skills Demonstrated

- Vision-language-action pipeline design
- Language intent parsing
- Safety-first driving policy design
- Explainable decision logic
- Autonomous-driving project framing

## How To Improve

- Replace synthetic scene cues with object detection outputs.
- Use a real language model for command parsing.
- Add temporal memory across multiple frames.
- Evaluate against a labeled dataset of scene-command-action examples.
- Add CARLA simulation for closed-loop testing.
