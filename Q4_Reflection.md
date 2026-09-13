# Q4 – Reflection and Next Steps

## Key Learnings
The project provided practical experience in multi-agent architecture, orchestration, prompt engineering, data grounding, structured outputs, n8n workflow automation, evaluation and observability.

## Multi-Agent Learning
Separating planning, risk, status, milestone and stakeholder responsibilities made prompts and outputs more focused, while the Orchestrator provided centralized routing.

## Prompt Engineering
Effective prompts require explicit context boundaries, preservation of actual IDs/names, anti-hallucination rules, insufficient-data behavior and predictable output schemas.

## Data Grounding
Grounding is critical because fabricated dates, statuses, risks or milestones can lead to incorrect project decisions.

## Evaluation Learning
AI evaluation must consider the complete pipeline. The T1–T12 workflow exposed issues involving candidate generation, grounding, counting, scope, test-item preservation and evaluator alignment.

## Observability Learning
Langfuse helps distinguish model/prompt issues from workflow or routing issues and provides visibility into AI execution.

## Implementation Challenges
The build involved API authentication and JSON formatting, routing normal and evaluation requests, preserving all evaluation items, debugging evaluator alignment, handling an external API quota limitation and validating Langfuse traces.

## Limitations
- File-based project data
- Small baseline evaluation set
- Continued need for prompt/evaluator refinement
- Limited enterprise integrations
- No advanced RAG in the current implementation
- Human review remains valuable for consequential decisions

## Future Improvements
1. Jira/Azure DevOps integration
2. Enterprise RAG
3. Human approval checkpoints
4. Automated milestone notifications
5. Larger evaluation datasets
6. Role-based access control
7. Risk trend detection
8. Production monitoring
9. Fine-tuning if evaluation data justifies it

## Overall Reflection
The project demonstrates how agentic AI can augment project-management workflows by combining structured project data, specialist agents, orchestration and observability. The key principle is to generate useful project intelligence while remaining grounded in authoritative project information.
