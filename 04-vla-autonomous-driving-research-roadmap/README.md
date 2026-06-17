# VLA Autonomous Driving Research Roadmap

## Overview

This folder is a learning and expansion roadmap for building stronger Vision-Language-Action autonomous-driving projects. It connects the starter projects in this branch to real datasets, stronger models, and publishable portfolio work.

## Core Idea

Vision-Language-Action models for autonomous driving aim to connect:

- visual perception of road scenes
- language commands, questions, or explanations
- driving actions or planned trajectories

The starter projects in this branch use transparent logic so the pipeline is understandable before moving to larger neural models.

## Suggested Next Projects

1. Driving Scene Captioning
   - Input: road image
   - Output: caption such as "A pedestrian is crossing at a red light."

2. Command-Grounded Driving Action
   - Input: road image plus command
   - Output: stop, yield, slow down, keep lane, turn left, or turn right

3. Visual Question Answering for Driving
   - Input: road image plus question
   - Output: answer plus evidence

4. Segmentation-Guided Planning
   - Input: road segmentation mask
   - Output: safe action or waypoint proposal

5. End-to-End VLA Policy Prototype
   - Input: image sequence plus navigation text
   - Output: action sequence

## Public References

See `references.md` for sources and datasets that can be used ethically as inspiration or with proper citation.
