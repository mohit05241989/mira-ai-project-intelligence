# Q1 – Ideation

## Problem Statement
PMs/TPMs spend substantial time combining project documents, timelines, risk registers and task-board information into standardized project-management outputs. Mira addresses this through grounded AI agents.

## Use Case 1 – Project Plan Generation
**Pain point:** Manual planning can take 3–4 hours.  
**Solution:** Planner Agent uses project description and timeline to produce phases, activities, milestones, deliverables and timeline.  
**Inputs:** project description, timeline.  
**Outputs:** structured project plan.

## Use Case 2 – Risk Assessment
**Pain point:** Risk assessment can be inconsistent and time-consuming.  
**Solution:** Risk Assessor Agent analyzes supplied risks and produces category, challenge, impact and mitigation.  
**Inputs:** project description, risk data.  
**Outputs:** structured risk assessment.

## Use Case 3 – Weekly Status Reporting
**Pain point:** Weekly status preparation can take 1–2 hours.  
**Solution:** Status Reporter Agent summarizes actual task-board records by status and sprint.  
**Inputs:** task board and sprint.  
**Outputs:** completed, in-progress, blocked and to-do work plus status summary.

## Extended Use Case – Milestone / Blocked-Task Tracking
Mira identifies milestones and blocked/at-risk work using supplied timeline and task data.

## Success Metrics
1. Reduce plan preparation from hours to minutes.
2. Reduce weekly status preparation from 1–2 hours to minutes.
3. Maintain high factual accuracy against supplied project data with no invented project-specific facts in accepted outputs.

## Knowledge Base
- project_description.txt
- project_timeline.csv
- project_risks.csv
- sample_task_board.csv

## Why Multi-Agent?
The use cases have different reasoning and output requirements. Specialist agents provide focused prompts and responsibilities, while the Orchestrator provides routing and scalability.
