# Traffic Scene VQA and Action Policy

Notebook: `traffic_scene_vqa_action_policy.ipynb`

## Overview

This project prototypes a driving-scene visual question answering (VQA) and action recommendation system. It treats detected scene objects as the vision input, accepts natural-language questions, and returns answers plus driving actions.

## Problem Statement

Given a driving scene and a question such as:

- "Is it safe to move?"
- "What should the car do at the traffic light?"
- "Are there pedestrians ahead?"

Return:

- a concise answer
- a recommended high-level driving action
- an explanation grounded in scene evidence

## VLA Mapping

| VLA Part | This Project |
|---|---|
| Vision | Structured detections such as traffic lights, pedestrians, and vehicles |
| Language | Natural-language questions |
| Action | Stop, yield, slow down, or proceed |

## Workflow

1. Define synthetic driving scenes with detected objects.
2. Ask natural-language questions about each scene.
3. Match the question intent.
4. Answer the question using scene evidence.
5. Recommend a driving action.

## Skills Demonstrated

- Visual question answering design
- Scene graph style reasoning
- Language-conditioned action recommendation
- Explainable VLA decision output
- Autonomous-driving safety logic

## How To Improve

- Replace synthetic detections with YOLO, DETR, or Grounding DINO outputs.
- Use a vision-language model for richer scene captions.
- Add temporal questions about video sequences.
- Evaluate with human-written driving questions.
- Add a planner that converts high-level actions into waypoints.
