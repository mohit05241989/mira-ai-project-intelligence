# mira-ai-project-intelligence
Mira – AI-Powered Project Intelligence Assistant

IK Capstone Project Submission

Organization: Nexora Pvt. Ltd.
Client Project: ABCDE Ltd. – 6-Month AI Adoption Project
Platform: n8n
Observability: Langfuse

1. Executive Summary
Mira is an AI-powered Project Intelligence Assistant designed to support Project Managers and Technical Project Managers with project planning, risk assessment, weekly status reporting, milestone/blocked-task tracking and stakeholder communications.
Mira uses a multi-agent architecture. An Orchestrator routes requests to specialist agents, while supplied project files provide the grounding context.

2. Business Problem
Key PM/TPM pain points addressed:
Project-plan preparation can take 3–4 hours.
Weekly status-report preparation can take 1–2 hours.
Risk assessments may be inconsistent.
Milestones and blocked work can be missed.
Project documentation is not always standardized.

3. Solution
Core capabilities:
Project Plan Generation
Risk Assessment
Weekly Status Reporting
Milestone / Blocked-Task Tracking
Stakeholder Update Generation

4. Architecture
PM / TPM
   |
Mira API
   |
Orchestrator / Router
   |
   +--> Planner Agent
   +--> Risk Assessor Agent
   +--> Status Reporter Agent
   +--> Milestone Tracker
   +--> Stakeholder Update Agent
   |
Structured Response

Grounding:
project_description.txt
project_timeline.csv
project_risks.csv
sample_task_board.csv

Observability:
Langfuse

5. Multi-Agent Design
Agent
Responsibility
Orchestrator
Understands request and routes it
Planner Agent
Generates grounded project plans

Risk Assessor Agent
Produces project-specific risk assessments

Status Reporter Agent
Summarizes task-board progress

Milestone Tracker
Identifies milestones and blocked/at-risk work

Stakeholder Update Agent
Creates stakeholder communications

6. Orchestration
Mira uses a Router/Dispatcher pattern. Project-plan requests go to Planner; risk requests to Risk; status requests to Status; milestone/blocked-task requests to Milestone; stakeholder requests to Stakeholder Update.

7. Data Grounding
Mira uses:
project_description.txt
project_timeline.csv
project_risks.csv
sample_task_board.csv

Agents are instructed to preserve actual IDs, task names, milestones and risks and to request more information when context is insufficient.

8. Evaluation
A T1–T12 baseline evaluates grounding, insufficient-data handling, task/status accuracy, milestone accuracy and scope adherence. The evaluation workflow preserves all 12 test cases through specialist and judge stages.

9. Observability
Langfuse is connected to provide AI execution traces for troubleshooting, performance analysis and evaluation.

10. Extended Capability
Mira identifies blocked or at-risk tasks. The supplied task board includes T024 – Security review of AI infrastructure – Blocked.

11. Limitations
Current limitations include file-based project data, a relatively small baseline dataset, limited enterprise-system integrations, and the need for continued prompt/evaluator refinement.

12. Future Enhancements
Jira/Azure DevOps integration
RAG-based enterprise knowledge retrieval
Human-in-the-loop approval
Automated milestone notifications
Larger evaluation datasets
Role-based access control
Advanced risk prediction
Production monitoring


