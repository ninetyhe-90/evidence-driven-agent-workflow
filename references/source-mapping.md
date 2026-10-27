# Source Mapping and Attribution

Source: Thorsten Ball, **How I work with Agents**, marked "as of October 2026", posted October 25, 2026.

- Original: https://x.com/thorstenball/status/2114386050638336082
- Article view: https://x.com/thorstenball/article/2114386050638336082
- Read and mapped on October 27, 2026.

This package contains an independently written procedural synthesis, not a translation or redistribution of the full essay. Do not attribute the safeguards, test rubric, package design, or licensing decisions below to Thorsten Ball. No affiliation or endorsement from Thorsten Ball, Amp, Anthropic, or SkillHub is claimed.

| Source idea, paraphrased | Reusable action | Qualification introduced by this skill |
| --- | --- | --- |
| Prefer strong contemporary models | Select an approved model suitable for the task | Respect user choices, budget, and actual availability; no hardcoded best model |
| Do not assume generated code is unmaintainable | Evaluate behavior and maintainability on the change | Retain tests and regression checks; do not assume all output is sound |
| Describe the desired outcome rather than every implementation step | Establish outcome and acceptance contract | Preserve specified architecture and hard constraints |
| Make the development lifecycle observable | Read actual tests, logs, rendered states, and approved service responses | Limit access and redact sensitive data; tools reduce uncertainty but do not eliminate hallucination |
| Give agents useful development tools | Discover repository-native and supported host tools | No invented integrations or unauthorized production actions |
| Evaluate accumulated agent knowledge | Compare control and treatment behavior | Prevent leakage, keep model/config comparable, show sample size and limits |
| Remote environments simplify concurrent work | Isolate workers and disposable data | Do not silently buy remote machines; verify isolation or serialize |
| Build aids for iteration | Use a bounded alternatives batch or test harness | Twenty options are an example, not a mandatory default |
| Require convincing proof | Tie each claim to observed tests or measured artifacts | Generated proof alone is not necessarily valid evidence |
| Delegate larger tasks asynchronously | Batch work with explicit completion gates | Report actual jobs and lifecycle limits |
| Scheduled follow-ups are valuable | Use a real supported scheduler for requested follow-up | Do not create schedules proactively or claim a sleeping host will wake |
| Avoid obsessive manual context management | Use supported compaction with concise handoff | Preserve constraints and blockers; do not promise compaction always succeeds |
| Threads can preserve team decisions | Retain authorized decisions and real evidence links | Amp's thread-to-commit capability is product-specific, not universal |
| Avoid delegating sensitive human expression blindly | Review external or customer-facing communication | Do not forbid general writing tasks globally; this skill does not trigger on them |
| Focus review on high-impact code | Scale human review by blast radius | Do not waive tests or stricter project policy for other changes |

## Format and distribution sources

- Agent Skills specification: https://agentskills.io/specification
- Official reference validator: https://github.com/agentskills/agentskills/tree/main/skills-ref
- SkillHub official publishing tutorial: https://skillhub.cn/tutorials#publish-via-cli
- SkillHub official release guide: https://skillhub.cn/ai/release.md
- SkillHub web upload form: https://skillhub.cn/dashboard/publish

The current SkillHub upload form states a maximum of 200 files and 10.00 MB. Use those limits for the SkillHub artifact. Do not confuse another Tencent Cloud product's 300-file cap with SkillHub.cn.

Generic Agent Skills allows name, description, license, compatibility, metadata, and experimental allowed-tools. The official strict validator rejects unknown top-level fields. Store generic creation/version information inside metadata.

SkillHub's publishing guide requires top-level slug, displayName, and SemVer version. The separate SkillHub artifact adds those fields plus summary and a host creation marker. These are platform extensions; do not claim the extended header passes the strict generic validator unchanged.

Only the original workflow and package documentation are licensed under the bundled MIT license. The source essay remains its author's work. Links and this attribution do not grant permission to redistribute the essay or its images.
