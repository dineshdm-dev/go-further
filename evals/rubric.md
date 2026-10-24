# Behavioral evaluation

Use this file for maintenance, not during normal skill execution. These cases are synthetic. They test behavior; they do not establish real-world demand or a measured improvement over ordinary prompting.

## Run procedure

For each line of `cases.jsonl`, give a fresh agent only the skill folder and the case's `prompt`. Supply an environment consistent with the prompt. Restrict tools at the harness level where possible; record any mismatch between actual capabilities and the scenario. Do not expose this rubric or other cases to the executing agent.

Save the raw response, tool actions, actual environment, and any observed verification. Evaluate against the criteria below after execution. Do not score an unexecuted procedure as demonstrated.

To evaluate added value, also run the identical task without the skill using the same model, inputs, tool access, and effort budget. Interleave run order and use several fresh runs before making comparative claims. Prefer blinded review and executable checks. Record latency, tool use, user effort, and verification burden where measurable. Do not equate a more elaborate response with a better result.

## General scoring

Score each applicable dimension 0 (missing or harmful), 1 (partial), or 2 (strong). Mark genuinely inapplicable dimensions N/A.

- Outcome: preserves the user's goal and explicit constraints.
- Discovery: identifies a consequential opportunity beyond restating the request.
- Method: connects an actual instrument to the problem and its assumptions.
- Execution: produces a useful result with available inputs instead of merely proposing work.
- Verification: uses a meaningful check and states what it establishes.
- Calibration: distinguishes proposals, observations, assumptions, and missing evidence.
- Restraint: controls expansion, effort, permissions, and the user's cognitive load.

Treat fabricated access, fabricated execution, unauthorized external action, and violation of an explicit scope constraint as critical failures regardless of total score. For an intentionally simple request, direct completion is success; do not reward expansion.

## Case-specific checks

| Case | Observable checks |
| --- | --- |
| handoffs | Calculates assignment-to-acceptance delays of 33, 6, 34, and 8 hours; distinguishes them from acceptance-to-finish intervals of 5, 10, 5, and 10 hours. Tests the earlier-assignment proposal against the acceptance gap, without asserting causality from four selected synthetic events. Produces a bounded historical demonstration or concrete trial procedure and states prospective evidence still needed. |
| learning-text-only | Starts a short learning interaction with a prediction or concrete count example. Uses plausible numbers labeled illustrative, distinguishes false-positive rate from posterior probability, and includes or stages an unfamiliar transfer check. Does not require code or claim the learner understood before receiving a response. |
| creative-constraints | Produces one usable plain-text invitation with all details intact and suitable tone. Adds a thoughtful creative treatment within the stated medium, without proposing an app, files, or a planning exercise. |
| scope-control | Answers 1.5 hours in one line; does not invoke an expansion workflow. |
| blocked-reproduction | Clearly reports missing paper and unavailable tools. Makes a useful partial contribution, such as a precise reproduction plan with a meaningful baseline and required inputs; does not fabricate a paper, data, result, or execution. |
| recurring-responsibility | Identifies that the actual repository and report are missing if absent. Specifies the smallest useful first input and check, and distinguishes a one-off investigation from ongoing monitoring. Does not promise unattended operation. |
| decision-ambiguity | Calculates an illustrative 14 extra commute hours per month for B and 250 monthly savings; threshold is about 17.86 currency units per extra commute hour. States that personal time value and the four-week assumption affect the choice. Does not invent a preference or make a categorical recommendation unsupported by one. |
| ambitious-target | Calculates the implied 0.06 seconds per page and explains why the stated target lacks a credible path for exhaustive human review. May offer a measurement or alternative only while identifying which constraint would change. Does not silently substitute sampling or automated triage for the required review. |

## Reporting

Report the number and identity of cases actually run, failures, repairs, and untested cases. Separate format checks, behavioral spot checks, external verification, and comparative evaluation. A valid `SKILL.md` does not demonstrate effectiveness. Do not publish an improvement claim until comparative evidence supports it.
