# Controlled Knowledge Evaluation

Use this procedure only when the user wants to test whether AGENTS.md, a skill, or another instruction resource improves agent behavior. Loading a skill does not train model weights. Writing a rule does not prove it is used, correct, or useful.

## Define the experiment before running

1. Name the exact behavior to improve: reproducing a bug before editing, selecting a valid test, providing an observed result, respecting a permission boundary, or completing a representative task.
2. Create representative tasks plus edge cases. Keep expected answers and rubrics out of worker prompts. Use held-out cases if the instruction was developed against known examples.
3. Choose a permitted run and cost budget. The source mentions five blind agents as a sketch, not a guaranteed statistical design; do not spawn paid workers without a budget.
4. Freeze model/configuration, starting revision, tools, permissions, workload, and scoring rubric. Record unavoidable differences.

## Assign conditions

- Control: original task instructions and baseline project rules.
- Treatment: the same baseline plus the tested knowledge resource.
- Give fresh isolated context to each worker; verify separate files/worktrees or serialize runs.
- Do not give control workers the treatment resource. If the host always injects it, report contamination and do not call the comparison controlled.
- Blind the scorer to condition labels when practical. Never give workers the hidden answer or feedback from previous runs during the scored trial.

## Score observations

Record per run: task ID, condition, model/config, revision, tool observations, result, relevant constraints, score, and actual cost/time if returned. Missing metrics remain unknown.

Separate task success, regression or policy failures, evidence quality, and cost/latency. Do not collapse them into a single flattering number. Use actual behavior, not the worker's statement that it followed the instructions.

Report raw results and aggregate counts with sample size. A small pilot can reveal failures but cannot establish a general causal improvement. Disclose noise, contamination, varying task difficulty, and unblinded judgment.

## Decide what to retain

Keep instructions that improve an observable behavior without unacceptable costs or violations. Revise instructions that were ignored, vague, harmful, or redundant. Run held-out checks after revision. Do not delete project safeguards just to improve success rate.

## Example, not an executed result

Task: identify and fix a local input-validation bug. Treatment: require reproduction and regression evidence. Observable rubric: baseline failure reproduced, focused patch, regression passes, no unauthorized changes, truthful limits. Report each dimension separately; do not assert treatment wins until the runs exist.
