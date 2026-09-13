# Mira Evaluation Results

## Baseline Evaluation Run

The Mira evaluation workflow was executed against all 12 baseline test cases (T1–T12).

The n8n trial used for the evaluation has subsequently ended, so the results below are the **captured results from the last successful baseline evaluation run**. They are retained as historical baseline evidence and are not presented as a new post-fix rerun.

## Overall Results

| Metric | Result |
|---|---:|
| Total tests | 12 |
| Passed | 5 |
| Failed | 7 |
| Pass rate | 41.67% |
| Average score | 71.67 / 100 |

## Test-by-Test Results

| Test | Capability | Result | Score |
|---|---|---|---:|
| T1 | Detailed project plan | FAIL | 70 |
| T2 | Vague project plan / insufficient information | PASS | 100 |
| T3 | Detailed risk assessment | FAIL | 60 |
| T4 | Vague risk assessment / insufficient information | PASS | 100 |
| T5 | Sprint 3 status report | FAIL* | 60 |
| T6 | Status request without task data | PASS | 100 |
| T7 | Top 3 project risks | PASS | 100 |
| T8 | Blocked / at-risk task identification | PASS | 100 |
| T9 | Vague 2-week project request | FAIL | 20 |
| T10 | Current task counts | FAIL | 50 |
| T11 | Upcoming milestones | FAIL | 30 |
| T12 | Sprint 2 stakeholder update | FAIL | 70 |

## Key Findings

### T1 – Detailed Project Plan
The generated plan contained phases, milestones and deliverables, but it also introduced quantitative goals such as reducing delivery delays by 15% and lowering operational costs by 10%. These goals were not supported by the supplied project description, so the evaluator marked the test as failed.

### T2 – Vague Project Plan
Mira correctly identified that the request did not contain enough information and asked for additional project details rather than generating a complete plan. This test passed.

### T3 – Detailed Risk Assessment
The response produced categorized risks, but the evaluator considered some of the risks too generic rather than sufficiently specific to the logistics/AI project. This test failed.

### T4 – Vague Risk Assessment
Mira correctly recognized insufficient information and did not invent project-specific risks. This test passed.

### T5 – Sprint 3 Status
The candidate response referenced actual Sprint 3 task records, including T007, T008, T009 and T025. However, the captured evaluator result indicated that the evaluator could not verify the task grounding in its evaluation context and marked the test as failed.

*Note: T5 is retained exactly as recorded in the baseline run. The candidate output itself contained evidence for the actual Sprint 3 task names, so this result also exposed an evaluation-context/alignment issue that was subsequently investigated.

### T6 – No Task Data
Mira correctly indicated that task data was unavailable and did not fabricate task statuses. This test passed.

### T7 – Top 3 Risks
Mira identified three risks from the supplied project risk data without inventing unrelated risks. This test passed.

### T8 – Blocked / At-Risk Tasks
Mira correctly identified T024 – Security review of AI infrastructure as Blocked and included the supplied due date. This test passed.

### T9 – Vague 2-Week Project
The response generated a detailed plan despite the request providing no scope, goals or deliverables. The evaluator therefore marked it as failed.

### T10 – Current Task Counts
The response attempted to provide Done, In Progress, To Do and Blocked counts, but the captured result contained an incorrect To Do count. The supplied task board contains 25 tasks: 5 Done, 3 In Progress, 16 To Do and 1 Blocked. This exposed a counting/grounding weakness.

### T11 – Upcoming Milestones
The response returned real milestones from the timeline, but it did not sufficiently restrict the result to the requested next-two-week window. This test failed.

### T12 – Sprint 2 Stakeholder Update
The response was professional and referenced Sprint 2 work, but it also mentioned Sprint 3 in the next steps. This violated the requirement to keep the update within Sprint 2 scope.

## Evaluation Pipeline Findings

The baseline run also helped identify implementation issues in the evaluation workflow:

- The evaluation pipeline was initially collapsing multiple test cases into a single item in several Code nodes.
- The evaluation entry point and normal Mira API entry point required separate routing.
- The project context needed to be explicitly preserved and passed to each evaluation case.
- The evaluation judge needed to retain the correct test ID and corresponding candidate answer.
- The T5 result highlighted the importance of ensuring that the judge receives the same grounded context used by the candidate.

These findings were used to improve the workflow's evaluation design and data flow.

## Interpretation

This baseline demonstrates that Mira can successfully handle several grounded PM/TPM scenarios, particularly insufficient-information handling, risk lookup, and blocked-task identification. It also identifies clear improvement areas around strict grounding, exact counting, time-window filtering, sprint-scope control, and evaluation alignment.

Because the n8n trial ended after this baseline run, no claim is made here that the 12 tests were rerun after every subsequent workflow change.

## Submission Note

The figures in this document should be described as the **captured baseline evaluation results**. If a future n8n environment is available, the recommended follow-up is to rerun T1–T12 after the latest workflow fixes and record the new results separately rather than overwriting this historical baseline.
