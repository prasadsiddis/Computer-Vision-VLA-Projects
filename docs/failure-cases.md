# VLA Baseline Failure Cases

These examples document where the current rule-based VLA baselines are expected to fail. The purpose is to make the project more research-oriented: a strong VLA system should explain uncertainty, not only output actions.

## Failure Case 1: Ambiguous Pedestrian Intent

**Scenario:** A pedestrian is near the crosswalk but not clearly entering the lane.

**Current baseline behavior:** The rule policy may immediately return `yield`.

**Why this can fail:** A safe driving policy should distinguish between a pedestrian waiting on the sidewalk, stepping into the road, or moving away from the route.

**Research upgrade:** Add temporal cues from consecutive frames and classify pedestrian motion intent.

## Failure Case 2: Poor Visibility With Sparse Object Detections

**Scenario:** Rain, fog, or nighttime driving reduces visibility, but object counts remain low.

**Current baseline behavior:** The rule policy may under-estimate risk if no nearby object is detected.

**Why this can fail:** Low object count in poor visibility can mean sensor uncertainty, not safety.

**Research upgrade:** Add a visibility confidence score and make the action policy conservative when perception confidence is low.

## Failure Case 3: Map Context Missing During Turns

**Scenario:** The ego vehicle is preparing for a left or right turn, but lane topology and crosswalk geometry are unavailable.

**Current baseline behavior:** The rule policy may use only object distance and traffic-light state.

**Why this can fail:** Turning decisions depend on lane graph, route intent, crosswalks, and conflicting actor forecasts.

**Research upgrade:** Use Argoverse 2-style HD map features and actor trajectory forecasts before selecting a turn action.

## Failure Case 4: Language Command Conflicts With Scene Safety

**Scenario:** A command says "go around the vehicle," but the scene has a cyclist in the adjacent lane.

**Current baseline behavior:** A command-grounding policy may over-prioritize the language instruction.

**Why this can fail:** VLA driving systems need to resolve conflicts between user commands and safety constraints.

**Research upgrade:** Add a safety arbitration layer that can override language commands when perception indicates risk.

## Evaluation Follow-Up

Future experiments should tag each failure with:

- scene condition
- missing perception feature
- unsafe action risk
- expected safer action
- required model upgrade
