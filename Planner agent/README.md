# Planner Agent

## Overview
The Planner Agent is an orchestrator that formulates structured interview schedules and study roadmaps based on a candidate's readiness match. It defines the optimal sequence of technical topics to assess.

## Inputs
- **Readiness Match JSON**

## Outputs
- **Plan JSON**: Topic lists, suggested durations, and difficulty progression.

## Usage
```python
from planner_agent import generate_plan

plan = generate_plan(match_results)
```
