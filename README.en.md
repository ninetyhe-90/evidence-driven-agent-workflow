# Evidence-Driven Agent Workflow

[中文](README.md) · **English** · [日本語](README.ja.md)

Turn autonomous coding into an outcome contract, bounded execution, and a result that can be verified.

Use this skill for feature implementation, debugging, performance optimization, or controlled evaluation of AGENTS.md and skills. Establish the desired result, observe the project, run bounded experiments, verify the behavior, and deliver evidence. Keep the process short for small reversible changes.

## Origin

Inspired by Thorsten Ball's [How I work with Agents](https://x.com/thorstenball/status/2114386050638336082). This is an independently written workflow, not a full translation or an official Thorsten Ball/Amp skill.

It retains outcome-first instructions, tool-based observation, batch iteration, evidence gates, and risk-scaled review. It does not mandate the latest model, waive most code review, or authorize deployment and customer contact. The [source mapping](references/source-mapping.md) explains all fifteen source ideas and added qualifications.

**A skill loads task instructions. It does not train model weights, guarantee persistent memory, or establish a performance improvement without evaluation.**

## Capabilities

- Convert ambiguous requests into observable acceptance criteria while preserving project constraints.
- Ground decisions in actual code, tests, logs, and rendered behavior.
- Use limited hypotheses and experiments rather than indefinite retries; verify resource isolation before parallel work.
- Separate UI appearance, behavior, persistence, and performance claims.
- Prioritize human review by consequences while retaining required tests and project review policies.
- Evaluate instruction resources in fresh control/treatment contexts; report contamination and small-sample limits.

## Usage

Import the standard package into a directory-based Agent Skills client, or place its skill directory in the client's documented skill location. WorkBuddy's user-level location is `~/.workbuddy/skills/evidence-driven-agent-workflow/`; its local profile includes a creation marker. Other clients may use different locations.

Example requests:

> Use evidence-driven-agent-workflow to fix empty-string validation in this parser. Preserve the API, do not deploy, and provide actual regression evidence.

> Optimize this search endpoint with the skill. Measure the baseline first and preserve authorization and response shape. Report observed results even if the target is missed.

> Evaluate whether this AGENTS.md improves reproduction-before-edit behavior. Confirm a run budget and use isolated control/treatment conditions.

Expected delivery: changed files, meaningful checks, observed outcomes, unverified paths, risks, and required review. These examples describe expected behavior, not executed test results.

## Distribution profiles

| File | Target | Header |
| --- | --- | --- |
| `evidence-driven-agent-workflow.zip` | Generic Agent Skills clients | Standard fields; version and creation marker inside metadata |
| `evidence-driven-agent-workflow-skillhub.zip` | SkillHub web upload | Top-level slug, displayName, version, summary, and creation marker; SKILL.md at ZIP root |

Both profiles contain identical instructions and resources. The standard creator's packager keeps the skill directory; the SkillHub artifact removes that wrapping directory. **Platform extensions are not strict generic specification fields.**

SkillHub submission values:

- Slug: `ninetyhe-evidence-driven-agent-workflow`
- Display name: `证据驱动的 Agent 工程工作流`
- Version: `1.0.0`
- Description: an outcome-first engineering workflow with bounded experiments, real verification, and risk-scaled review.
- Upload: https://skillhub.cn/dashboard/publish

The observed web limit is 200 files and 10 MB total. The package contains text only: no nested archives, runtime scripts, credentials, or source-article images. Slug availability and approval remain platform decisions.

The currently installed SkillHub CLI 2026.3.7 has no publish command. No platform dry-run was performed, and no automatic upgrade was attempted. Use the web artifact, or follow the [official CLI guide](https://skillhub.cn/tutorials#publish-via-cli) to set up a publishing-capable release. This task prepares packages only; it does not submit or publish them.

## Contents

```text
evidence-driven-agent-workflow/
├── SKILL.md
├── README.md
├── README.en.md
├── README.ja.md
├── LICENSE.txt
├── assets/task-contract.md
└── references/
    ├── workflow.md
    ├── knowledge-evaluation.md
    ├── source-mapping.md
    └── acceptance-examples.md
```

The main skill uses concise English instructions and loads references on demand. Respond in the user's language; the three READMEs need not be loaded for every task.

## Boundaries and evaluation

No fixed model, API key, cloud service, or runtime script is required. Coding still needs host-provided file and testing tools. If unavailable, provide an analysis-only result and name the missing verification. Do not install software, spend money, deploy, send messages, or schedule jobs without authorization. Sandboxing does not grant business permissions.

Format validation and example review do not demonstrate improved engineering success. Start with the [ten acceptance cases](references/acceptance-examples.md), then use [controlled evaluation](references/knowledge-evaluation.md) on representative tasks.

## License

The original workflow and package documentation use [MIT](LICENSE.txt). Thorsten Ball retains rights to the source article. Its full text and images are not distributed. No endorsement by Thorsten Ball, Amp, Anthropic, or SkillHub is claimed.
