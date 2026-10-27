# Workflow Details

## Convert a request into a testable contract

Identify the desired behavior, constraints, baseline, success measure, allowed actions, and stop condition. Reuse the user's specification rather than replacing it with a preferred architecture. For a small bug, use a few sentences; avoid creating an unnecessary plan document.

Example, not a benchmark: "Reduce response time for the existing search endpoint without changing authorization or response shape. First measure an agreed sample dataset and workload. Compare latency and error rate before and after. Request approval before adding paid infrastructure."

Treat "make it fast" as a direction, not an already-defined measurement. Clarify whether the user cares about p95 latency, throughput, CPU, startup time, cost, or a combination. Measure one stable workload, retain failed runs, and state any baseline that cannot be reproduced.

## Make reality accessible without granting unlimited access

Discover project-native commands, tests, logs, browser tools, and approved APIs. Read only task-relevant authorized data. Do not expose secrets, unrestricted production consoles, or customer records simply because more context could help.

For each tool, identify the scope, credentials needed, read/write behavior, and evidence it can provide. Ask for missing permission or propose a local reproduction. Do not confuse a sandbox with authorization to change production state.

## Use bounded experiments

Record candidate explanation, predicted observation, discriminating test, result, and next action. Prefer a few cheap checks over editing several unrelated components at once. Reject hypotheses on evidence, not on agent confidence.

When exploring UI alternatives, generate the smallest batch that helps the user decide. Add a comparison page or test harness when it reduces repetitive interaction. Label generated options as alternatives, not validated user preferences.

Parallelize independent checks only after verifying file, branch, port, data, and service isolation. Never infer isolation from separate chat histories. Allocate resource limits and preserve failed experiments.

## Match evidence to the claim

A successful build proves that the build completed, not that a customer flow works. A screenshot proves a rendered moment, not a completed transaction. A tool receipt proves an action was dispatched, not that a remote state changed. A generated test is useful only after its assertions and execution are inspected.

Record at least: the command or action, input/workload, tested revision, relevant environment, observed outcome, and limits. Use actual tool output or measured artifacts. Mark unavailable evidence explicitly.

For performance, compare the same setup, include sufficient repeated runs for the requested decision, and show dispersion when relevant. Do not silently remove outliers or claim a general speedup from one sample. Choose repetition count with the task budget instead of pretending a fixed count is universal.

## Scale review by consequences

Prioritize human attention on migrations, privilege boundaries, payment logic, shared critical modules, release systems, and irreversible external effects. Keep automated tests and normal review policy on lower-risk changes. Do not adopt the author's "fewer than five files" as a portable exemption.

Pause before deployment, customer communication, production writes, recurring tasks, or new spending unless the user already authorized that exact scope. Keep execution logs free of credentials.

## Keep asynchronous work honest

Separate running workers from future scheduled jobs. A background process may end when the host session exits. A reminder in text is not a scheduler entry. Confirm scheduler ID internally, delivery destination, and offline behavior through the host's supported interface only when requested.

Keep the status explicit: running, verified, blocked, or awaiting review. Do not tell the user to wait on a job that was never created.

## Retain decisions rather than raw transcripts

When permitted, retain the problem, decision, alternatives rejected, evidence locations, and unresolved limitations. Link to a commit only if it really exists; do not fabricate IDs. Keep a concise handoff after compaction, not an unbounded copy of logs or secrets.

Treat each persisted rule as a hypothesis about future usefulness. Evaluate repeated corrections instead of endlessly appending instruction files.
