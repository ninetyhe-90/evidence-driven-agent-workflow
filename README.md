# Evidence-Driven Agent Workflow

**中文** · [English](README.en.md) · [日本語](README.ja.md)

把“让 AI 自己做完”变成目标明确、权限有边界、结果可验证的工程流程。

这个 Skill 给编码 Agent 使用，适合实现功能、排查 bug、性能优化，以及评估 AGENTS.md / Skill 是否真的改善了行为。它会要求 Agent 先说明要达到什么结果，再观察现有项目，做有限实验，执行验证，最后拿实际证据交付。小改动走短流程，不强制复杂规划。

## 从哪里来

灵感来自 Thorsten Ball 的 [How I work with Agents](https://x.com/thorstenball/status/2114386050638336082)。这里是独立编写的流程，不是全文翻译，也不是作者或 Amp 的官方 Skill。

保留了结果先行、工具观测、批量迭代、证据验收和风险分层。没有把“永远换最新模型”“只看少数文件”“自动部署和联系客户”写成无条件命令。15项原文观点与转换边界见 [来源映射](references/source-mapping.md)。

**Skill 让模型在任务中加载指令，不会训练模型权重，不保证持续记忆或自动提升能力。** 是否有效，需要受控任务验证。

## 能做什么

- 把模糊要求转成可观察的验收条件，尊重已有技术栈和限制。
- 用真实代码、测试、日志和渲染结果判断，不编“运行成功”。
- 用有限假设和实验排查，不无休止试错；并行前检查文件与资源隔离。
- 对实际行为和性能分别取证，不把截图当后台持久化证明。
- 将人的审查优先放在高影响区域，同时保留全部必要测试和项目审查规则。
- 用新上下文、对照/处理组和明确指标评估知识指令；发现污染就如实说明。

## 怎么用

在支持目录式 Agent Skills 的客户端导入标准包，或将技能目录放到该客户端的技能目录。WorkBuddy 的用户级目录为 `~/.workbuddy/skills/evidence-driven-agent-workflow/`；本机安装副本带有创建标记。其它客户端的安装位置以其文档为准。

可直接给 Agent 这些任务：

> 用 evidence-driven-agent-workflow 修复这个解析器的空字符串校验 bug，保留 API，不部署。给出真实回归验证。

> 用这个 Skill 优化搜索接口。先测现有延迟，保留鉴权和响应结构；没有达到目标就报告实际结果，不要补数字。

> 评估这份 AGENTS.md 是否让 Agent 更愿意先复现再修改。使用可隔离的对照实验，先确认运行预算。

预期交付：改了哪些文件、实际执行了什么检查、观察到什么、哪些没有验证、还有什么风险或审批。示例是行为要求，不是已完成的实测结果。

## 两个分发版本

| 文件 | 用途 | 元数据 |
| --- | --- | --- |
| `evidence-driven-agent-workflow.zip` | 通用 Agent Skills 客户端 | 官方标准字段；版本和创建标记放在 metadata 中 |
| `evidence-driven-agent-workflow-skillhub.zip` | SkillHub 网页上传 | 增加顶层 slug、displayName、version、summary 与创建标记；SKILL.md 直接在ZIP根目录 |

两份正文与资源相同。通用 ZIP 由官方创建器配套打包脚本生成，保留技能目录；SkillHub ZIP 使用无外层目录布局。**SkillHub 扩展字段不能冒充严格通用标准字段**，不要用扩展版宣称通用校验通过。

SkillHub 信息：

- Slug：`ninetyhe-evidence-driven-agent-workflow`
- 显示名：`证据驱动的 Agent 工程工作流`
- 版本：`1.0.0`
- 描述：`让编码 Agent 按目标、观察、有限实验、真实验证与风险审查完成工程任务；不编实测，不越权部署。`
- 发布入口：https://skillhub.cn/dashboard/publish

当前网页限制是最多200个文件、总大小不超过10MB。包只含纯文本，不含嵌套压缩包、可执行脚本、凭据或原文章图片。Slug 是否被占用和审核是否通过由平台决定。

当前本机 SkillHub CLI 2026.3.7 不支持 publish，未运行平台 dry-run，不自动升级。可直接使用网页上传文件；需要CLI时，按 [官方教程](https://skillhub.cn/tutorials#publish-via-cli) 配置支持发布的版本。此任务只准备上传包，没有提交审核或发布。

## 文件结构

```text
evidence-driven-agent-workflow/
├── SKILL.md
├── README.md
├── README.en.md
├── README.ja.md
├── LICENSE
├── NOTICE.md
├── assets/task-contract.md
└── references/
    ├── workflow.md
    ├── knowledge-evaluation.md
    ├── source-mapping.md
    └── acceptance-examples.md
```

SKILL.md使用简洁英文指令，Agent按需读取四份参考，输出使用用户语言。README只面向使用者；无需每次把三语说明载入上下文。

## 权限与限制

无固定模型、API Key或云服务依赖，无运行脚本。实际编码仍需要宿主提供文件和测试工具。没有执行环境时只给分析并说明未验证，不伪造结果。不会自动安装软件、支付、部署、发消息或创建定时任务。远程日志必须已有授权；隔离不等于操作授权。

形式校验和示例审阅不等于真实工程成功率提升。可以先用 [10个验收用例](references/acceptance-examples.md) 检查，再用 [受控评估](references/knowledge-evaluation.md) 测自己的任务。

## 许可证

本包原创流程与说明采用 [MIT](LICENSE)。原文章版权属于 Thorsten Ball；未打包全文或图片。未获作者背书，不是 Amp、Anthropic 或 SkillHub 官方项目。
