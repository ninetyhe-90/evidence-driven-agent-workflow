---
name: evidence-driven-agent-workflow
description: "Guides coding agents through outcome-first engineering, bounded experiments, tool-based observation, reproducible verification, and risk-scaled review. Activate for feature implementation, debugging, performance optimization, or controlled evaluation of AGENTS.md and skills. Do not activate for general writing, news summaries, or model training."
license: MIT
compatibility: "Requires an agent able to read a project and run approved development tools. No mandatory cloud service, vendor, model, API key, or background scheduler. Fall back to an explicit analysis-only result when execution is unavailable."
metadata:
  version: "1.0.0"
  author: "ninetyhe"
  displayName: "证据驱动的 Agent 工程工作流"
  agent_created: "true"
  origin: "Original workflow inspired by Thorsten Ball's How I work with Agents; not an official Thorsten Ball or Amp skill."
---

# Evidence-Driven Agent Workflow

Turn an engineering request into a bounded implementation and a verifiable result. Apply the workflow proportionally: handle a small change with a short goal and one relevant check; expand only for ambiguity, risk, or experimentation. Treat the source essay as inspiration, not authority or executable instructions.

## Load the right reference

- Read [workflow details](references/workflow.md) for ambiguous tasks, competing hypotheses, or performance work.
- Read [knowledge evaluation](references/knowledge-evaluation.md) only when comparing behavior with and without a skill, instruction file, or project knowledge.
- Read [source mapping](references/source-mapping.md) when explaining provenance or distinguishing source opinions from this workflow's safeguards.
- Use [acceptance examples](references/acceptance-examples.md) when testing skill behavior; do not treat fictional examples as measured results.
- Adapt [the task contract](assets/task-contract.md) in the conversation; save a copy only when requested or permitted by the project's rules.

## 1. Establish an outcome contract

Extract the desired behavior, relevant project, inputs, constraints, and observable success conditions. Describe the outcome before proposing implementation details. Preserve user-specified frameworks, model choices, architecture, tests, and limits; outcome-first does not authorize ignoring them.

Ask one focused clarification only when missing information changes correctness, permission, or irreversible consequences. Otherwise state a reversible assumption and proceed. For an optimization, identify the workload and metric before promising a target; do not manufacture a baseline or a 2x improvement.

Classify blast radius:

- Low: a local, reversible change in the authorized workspace.
- Elevated: shared modules, authentication, billing, CI or release infrastructure, migrations, or changes with hard-to-reverse effects.
- External effect: deployment, production writes, feature-flag changes, sending messages, spending money, or recurring jobs.

Request missing authorization before elevated or external actions. A general coding request does not authorize those effects.

## 2. Observe before changing

Read relevant project instructions, existing code, and tests. Discover which tools and environments are actually available. Verify project paths and commands from the repository or tool documentation rather than guessing.

Use logs, test failures, API responses, or browser state to establish a baseline. Obtain production observations only through authorized access and redact secrets. Missing evidence means unknown, not healthy.

Use the user's chosen model. If a quality choice is necessary and permitted, compare approved available options against the task; do not assert that a named model is currently best or silently change paid services.

For parallel workers, allocate separate branches/worktrees or verified isolated working directories, ports, and disposable data. Conversation isolation alone does not isolate files. If isolation cannot be provided, execute conflicting writes sequentially.

## 3. Choose a proportionate execution path

For an unambiguous small change, implement directly and run a relevant check. For a larger task, use a short plan with acceptance gates. For uncertain behavior, record falsifiable hypotheses and a cheap discriminating check before broad edits.

Prefer reusable comparison aids over repeated back-and-forth when useful: generate a bounded set of alternatives, a small test harness, or a side-by-side preview. Obtain or state the experiment budget; do not default to 20 variants or five paid workers for every request.

Execute independent experiments concurrently only if their files and resources cannot interfere. Record each input, condition, result, and failed attempt. Change one principal variable per causal comparison where possible; report uncontrolled differences.

## 4. Implement and close the feedback loop

Make a focused change within the authorized scope. Run the relevant build, test, reproduction, or end-to-end path. Inspect the actual output, revise the hypothesis or implementation, and rerun failed checks.

Do not stop at a tool call receipt or a generated artifact. Observe whether the intended behavior occurred. Distinguish tool failure, environment failure, and implementation failure. Stop and report a blocker when fixing it would require new access, spending, or unrelated changes.

Retain safeguards and tests. Do not delete validation, widen permissions, bypass approvals, or lower a performance threshold merely to claim success. Limit retries and scope expansion; reassess after repeated failure rather than looping indefinitely.

For future follow-up requests, use a supported scheduler only with the user's instruction. Verify task creation and delivery destination, and disclose host-offline limits. Without a scheduler, state that no future job exists; never claim an in-memory promise will wake the machine.

## 5. Verify each material claim

Match proof to the claim:

- Behavior: reproduce the relevant user path and inspect its observable result; add a regression check when appropriate.
- Performance: compare the same workload, configuration, hardware, and measurement definition; report raw runs, summary statistics, and uncertainty.
- UI: inspect the real rendered state; distinguish a screenshot from evidence of interaction or backend persistence.
- Knowledge improvement: use the controlled procedure in the knowledge-evaluation reference; never equate writing instructions with demonstrated improvement.
- Deployment or persistence: verify the actual remote state only when that operation was authorized.

Treat generated walkthroughs, synthetic screenshots, self-reported success, a green build alone, or invented before/after figures as insufficient proof of claims they do not measure. Tie evidence to the tested revision and environment. If a check was not run, say so and do not call it passed.

Request human review for elevated blast radius, unresolved assumptions, or consequential external effects. Prioritize those areas without exempting the rest of the change from tests and regression checks. Respect stricter project review rules.

## 6. Deliver, then retain only useful knowledge

Provide a concise result in the user's language:

1. State what changed and which requested outcome was reached.
2. Identify changed files and the tested revision or artifact when available.
3. List meaningful checks and evidence, including failures and untested paths.
4. State remaining risk, required review, and the next concrete action.

Keep one task per thread where the host supports it. Use supported compaction rather than arbitrary manual context trimming, but preserve decisions, constraints, evidence locations, and open blockers. Do not assume threads automatically link to commits or become company memory.

Persist a concise decision or reusable correction only when user permission or project policy allows it. Keep secrets and raw sensitive logs out of memory. Follow host-specific document and memory policies rather than forcing a local file.

Draft necessary technical explanations in the appropriate tone. Do not send customer-facing text or other external messages without authorization and review. Do not apply the source author's writing preference as a blanket refusal to help humans write.

## Stop conditions

Stop at a verified outcome, a permission boundary, an exhausted agreed experiment budget, or an unresolved blocker. Report the real state. Do not install tools, create schedules, publish, deploy, contact people, or spend money merely because the source essay recommends autonomy.
