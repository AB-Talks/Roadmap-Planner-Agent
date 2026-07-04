# Roadmap Agent

## Overview
The Roadmap Agent maps personalized career pathways. Given a candidate's resume and a target role, it generates weekly study milestones, project specifications, and resume improvement checkpoints.

## Inputs
- **Candidate Resume JSON**
- **Target Role/JD JSON**

## Outputs
- **Career Roadmap JSON**

## Usage
```python
from roadmap_agent import build_roadmap

roadmap = build_roadmap(resume_json, target_jd_json)
```
