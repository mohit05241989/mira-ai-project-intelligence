# Q2 – Build Mira

## 1. Solution
Mira is an n8n multi-agent workflow combining project data ingestion, context building, an Orchestrator, specialist agents, structured responses, evaluation and Langfuse observability.

## 2. Architecture
```text
User Request
     |
  Mira API
     |
 Orchestrator
     |
 Parse Route
     |
 +----+---------+-----------+-------------+
 |              |           |             |
Planner        Risk       Status       Milestone
 |              |           |             |
 +--------------+-----------+-------------+
                    |
             Stakeholder Agent
                    |
          Format Interactive Response
                    |
           Respond to Webhook
```

## 3. Grounding Pipeline
The workflow loads and parses the project description, project timeline, project risks and sample task board, then combines them into project context.

## 4. Orchestrator
The Orchestrator determines the requested capability and returns a structured route such as `plan`, `risk`, `status`, `milestone`, or `stakeholder_update`.

## 5. Specialist Agents
**Planner:** grounded project plan.  
**Risk Assessor:** project-specific risk assessment.  
**Status Reporter:** task-board status.  
**Milestone Tracker:** milestones and blocked/at-risk tasks.  
**Stakeholder Update:** professional stakeholder communication.

## 6. Prompt Engineering
Prompts use clear roles, explicit context boundaries, structured output requirements, grounding instructions, anti-hallucination rules and insufficient-data handling.

## 7. Data Grounding
Mira should not invent project goals, milestones, task IDs, task names, risk records, statuses or due dates. When information is insufficient, it should ask for the missing information.

## 8. Core Demonstrations
- Project plan from project description and timeline.
- Risk assessment from supplied risk data.
- Sprint 3 status from the task board.
- Blocked-task detection, including T024 where applicable.
- Sprint 2 stakeholder update.

## 9. Evaluation Architecture
```text
Evaluation Trigger
   -> Entry Point Routing
   -> Build Project Context
   -> T1–T12 Cases
   -> Evaluation Specialist
   -> Evaluation Judge
   -> Evaluation Results
   -> Evaluation Summary
```
The evaluation workflow was designed to preserve one item per test case throughout the specialist and judge stages.

## 10. Observability
Langfuse captures AI execution traces and supports debugging, performance analysis and evaluation.

## 11. Cost Strategy
A smaller model such as GPT-4o-mini is used for evaluation-oriented tasks where appropriate. Structured prompts and context reuse help control unnecessary token usage.

## 12. Evaluation Strategy
T1–T12 test detailed/vague planning, detailed/vague risk requests, sprint status, missing data, top risks, blocked tasks, task counts, upcoming milestones and stakeholder communication.
