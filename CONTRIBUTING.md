# Contributing / 参与指南

感谢参与 Iris Commons。任何语言、专业背景和GitHub经验水平的参与者都可以贡献。

你不需要先阅读整个仓库，也不需要先学会Discussion、Issue、分支或Pull Request。可以先把仓库地址交给你的AI，让它读取 [`AI_PARTICIPATION.md`](AI_PARTICIPATION.md) 和 [`AGENTS.md`](AGENTS.md)，并负责解释、检索、整理与GitHub操作。

Iris Commons提供的是可复制的人类—AI协作模板。使用本模板建立的项目彼此独立，不需要注册、互联、同步或向Iris Commons提交研究成果。

## 最简单的参与方式

向你的AI发送：

```text
阅读 https://github.com/Clearandcloudless/iris-commons 的
AI_PARTICIPATION.md、AGENTS.md、DATA_CLASSIFICATION.md、
COMMUNICATION_PROTOCOL.md、CONTENT_LIFECYCLE.md、
TEAM_GOVERNANCE.md 和 GOVERNANCE.md。

检查当前开放Discussions和Issues，根据我的背景和语言
推荐一个适合参与的议题或任务。

你负责GitHub流程，但任何公开提交前必须向我展示最终内容、
数据分类、提交位置和必要的审查或治理路径，并取得确认。
```

完整接入方法见 [`AI_PARTICIPATION.md`](AI_PARTICIPATION.md)。

## 可以贡献什么

- 提出项目构想中的漏洞、失败条件或反例；
- 分享真实的跨语言、跨文化或跨专业交流障碍；
- 提问、解释术语或帮助新参与者理解争议；
- 研究同类项目、开放标准和现有平台；
- 改进AI秘书协议、治理、数据模型和安全边界；
- 提交适合作为试验的公共研究课题；
- 翻译内容并指出无法准确转换的概念；
- 核查引用、复现实验或挑战已有结论；
- 担任内容、证据、方法、语言、安全、伦理、治理或实现审查者；
- 帮助分诊问题、整理路线图、维护Release或进行程序复核；
- 编写原型、自动检查和跨平台适配工具。

贡献不以代码、commit数量、英语能力或使用某种模型作为价值前提。

# 公开前的数据分类

本仓库是公开仓库。Discussion、Issue、评论、文件夹、分支和Draft Pull Request都不是私密空间。

所有原始对话、上传内容和AI草稿默认视为：

```yaml
classification: D1
classification_status: review-required
```

只有经过审查并由用户明确确认的 `D0 public-ready` 内容，才可以进入公开Discussion、Issue、评论、PR或仓库文件。

完整规则见 [`DATA_CLASSIFICATION.md`](DATA_CLASSIFICATION.md)：

| Level | Meaning | Public repository |
|---|---|---|
| `D0 public-ready` | 已确认可公开 | Allowed |
| `D1 review-required` | 需要隐私、版权、事实或安全审查 | Not yet allowed |
| `D2 restricted` | 仅限特定团队或机构 | Not allowed |
| `D3 prohibited` | 密钥、未经授权个人数据或重大伤害材料 | Never allowed |

不要把敏感内容放入名为`private/`、`internal/`或`restricted/`的公共目录。这些名称不产生访问控制。

# 选择最小的GitHub对象

完整交流规则见 [`COMMUNICATION_PROTOCOL.md`](COMMUNICATION_PROTOCOL.md)。

## Discussion

适合：

- 开放式交流和提问；
- 初步想法；
- 新成员介绍和寻找合作者；
- 资料分享；
- 项目方向和元讨论；
- 尚未形成明确任务或研究问题的内容。

当Discussion形成可追踪的问题、争议、任务、研究课题或修改目标时，应建立关联Issue。

GitHub Discussions未启用时，可以创建带有`type:discussion`标记的Issue临时代替。

## Issue

适合：

- 明确问题、假设或争议；
- 对现有设计的批评；
- 风险、遗漏和反例；
- 公共试验课题；
- 需要责任人、依赖、状态或验证标准的任务；
- 在形成正式修改前收集意见。

普通用户建议和想法不应自动成为仓库文件。

## Issue comment

适合：

- 补充证据、案例或资料；
- 解释术语和语言语境；
- 提出明确反对意见；
- 回答现有问题；
- 报告复现或验证结果；
- 提出替代方案、风险或失败条件。

可选前缀：

```text
[Evidence]
[Counterexample]
[Question]
[Interpretation]
[Alternative]
[Risk]
[Translation]
[Reproduction]
[Objection]
[Summary]
```

前缀不是参与门槛，AI可以帮助整理。

## Pull Request

适合：

- 修改项目文档；
- 增加或调整协议；
- 提交成熟提案或结构化研究结果；
- 修改Schema、自动检查或原型代码；
- 修订翻译版本；
- 更新Decision、Specification或长期知识状态。

大型修改应先创建Issue。没有仓库写权限的参与者应使用Fork和Pull Request。

## Review

审查本身是一种正式贡献。可以只审查一个明确维度：

```text
content-review
source-review
method-review
language-review
security-review
ethics-review
governance-review
implementation-review
```

请明确自己审查了什么、没有审查什么。重大内容不能由起草者作为唯一批准者。

# 长期内容放在哪里

完整路由规则见 [`CONTENT_LIFECYCLE.md`](CONTENT_LIFECYCLE.md)。

```text
docs/          explanatory guides and concepts
governance/    accepted governance and community rules
proposals/     formal RFC-style proposals
research/      questions, evidence, pilots and results
specs/         current normative specifications
decisions/     accepted decisions and rationale
schemas/       machine-readable schemas and enums
examples/      non-normative worked examples
translations/  maintained translations linked to source revisions
archive/       withdrawn, superseded or completed material
```

核心规则：

1. 开放交流优先进入Discussion；
2. 可追踪问题、假设和争议进入Issue；
3. 聚焦证据、反例和回复进入Issue comment；
4. 只有成熟、可复用的内容才成为文件；
5. 提案进入`proposals/`，但不自动成为规范或正式目标；
6. 只有经过治理审查的现行协议才能进入`specs/`；
7. 决策理由进入`decisions/`；
8. 普通旧版本由Git历史和Release保存，不要全部复制到`archive/`；
9. 不建立`users/<name>/`或通用`submissions/`投稿文件夹；
10. 文件按主题和功能组织，而不是按提交者身份组织。

## 从Issue升级为Proposal

一个Issue适合转为正式Proposal时，通常已经包含：

- 明确的问题；
- 具体方案；
- 替代方案；
- 风险和权衡；
- 实施或验证标准；
- 未解决问题；
- 原始Discussion、Issue和证据链接；
- 负责人或临时工作组；
- 需要的审查维度。

AI或参与者不应仅因为文本较长、点赞较多或讨论热烈，就把Issue自动升级为Proposal。

# 问题清单、排序和目标立项

详细规则见 [`TEAM_GOVERNANCE.md`](TEAM_GOVERNANCE.md)。

问题池建议状态：

```text
needs-context
needs-evidence
candidate
accepted-backlog
duplicate
out-of-scope
blocked
```

路线图建议使用：

```text
Now      当前周期必须处理
Next     下一阶段重点候选
Explore  尚需证据、试验或问题定义
```

AI可以建议评分、依赖和顺序，但点赞、评论数量、语言优势、传播范围或AI评分不能单独决定优先级。

正式立项目标至少应说明：

```yaml
title: goal title
problem: 要解决的问题
scope:
  - 包含内容
out_of_scope:
  - 不包含内容
deliverables:
  - 交付物
success_criteria:
  - 验证标准
owner: working-group-or-person
reviewers:
  - required-review-type
dependencies:
  - linked issue
stop_conditions:
  - 暂停或终止条件
```

立项只表示允许组织化开展工作，不代表预先接受结论。

# 团队角色和权限

项目应公开承担以下职能的人或团队：

- Maintainer / 项目维护者；
- Triage Steward / 议题管理员；
- Roadmap Steward or Council / 路线管理员或路线小组；
- Working Group / 临时工作组；
- Reviewer / 审查者；
- Release Steward / 发布管理员；
- Appeal Panel / 申诉小组。

小项目可以由少数人兼任多个角色，但重大内容必须有未参与起草的人类审查，起草者不能独立批准自己提交的治理、规范或高影响研究。

AI不是委员会成员，没有正式投票权、任命权和最终批准权。

# 语言规则

完整规则见 [`LANGUAGE_POLICY.md`](LANGUAGE_POLICY.md)。核心要求是：

> English for interoperability; native languages for thought.  
> 英文负责互操作，母语负责思想表达。

- 可以直接使用你最自然、最准确的语言；
- 不要求先翻译成英文才能参与；
- 请填写BCP 47风格的 `source_language`，如 `zh-CN`、`en`、`ja`；
- 参与者原文是其观点的权威表达；
- 译文和摘要属于派生内容，必须可追溯；
- 机器翻译必须标明；
- 仓库路径、文件名、字段ID、标签、状态值和接口使用英文；
- 英文桥接摘要是推荐项，不是参与门槛；
- 无法准确翻译的术语应保留原词并说明语境。

## 保留原始表达

AI可以帮助整理，但不要只提交经过AI重写的文本。对于重要观点，建议保留：

```markdown
## Original / 原文

参与者最初表达。

## Structured contribution / 结构化贡献

AI或人类整理后的版本。

## Translation notes / 翻译说明

语义差异、术语和不确定性。
```

短评论不必机械使用全部结构，但不得把AI改写冒充原作者原话。

# 区分事实、推断、观点和建议

正式贡献应尽量区分：

```text
Observation / Fact   观察或可核查事实
Inference            对事实的解释
Position             参与者当前判断
Proposal             建议采取的行动
```

AI不得把推断写成事实，也不得把多数意见写成已正式接受的项目立场。

# 阶段性摘要

长Discussion或Issue的摘要至少应保留：

- 已形成的共同认识；
- 主要分歧和各方依据；
- 关键证据与反例；
- 尚未核查的信息；
- 未解决问题；
- 下一步；
- 原始链接；
- AI参与和人类审阅情况。

参与者可以要求修正遗漏重要异议或扭曲原意的摘要。

# AI辅助披露

使用AI不降低贡献价值。需要披露的是AI承担了什么角色，而不是公开私人提示词或完整私人对话。

建议格式：

```yaml
ai_assistance:
  used: true
  provider: OpenAI
  model: model-name-or-unknown
  roles:
    - drafting
    - translation
    - critique
  human_reviewed: true
  human_modified: true
  factual_claims_checked: partial
```

AI提交内容时必须使用参与者授权的GitHub身份，不得冒充独立人类贡献者。

# 长期文件元数据

Proposal、研究记录、Decision和Specification建议包含：

```yaml
---
id: IRIS-RFC-0007
type: proposal
status: discussing
source_language: zh-CN
normative: false

origin:
  discussion: null
  issue: 42
  submitted_by: github-login

project_governance:
  owner: working-group-or-person
  required_reviews:
    - content-review
  decision_record: null

publication:
  classification: D0
  license: CC-BY-4.0

relations:
  supersedes: null
  superseded_by: null
---
```

公共元数据不得包含私人对话ID、内部文件路径、令牌或不必要的个人信息。

# 公开前确认

任何AI工具在创建Discussion、Issue、评论、分支、commit、Pull Request或Review之前，都应：

1. 向参与者展示最终公开文本或清晰的diff摘要；
2. 说明数据分类和选择的目标位置；
3. 说明需要的审查或治理路径；
4. 指出隐私、版权、事实和安全风险；
5. 取得明确确认；
6. 仅使用完成任务所需的最低权限；
7. 公开后返回链接和实际操作结果。

如果AI没有写权限，应提供完整的可复制草稿，不得要求参与者重新整理。

## 提交前检查

- [ ] 内容已经分类为`D0 public-ready`；
- [ ] 我有权公开这些内容；
- [ ] 已移除个人信息、密钥和敏感数据；
- [ ] 已检查第三方材料、数据和许可；
- [ ] 原始语言和必要的语言标识已经保留；
- [ ] 原文、译文、摘要、事实、推断和建议没有混为一体；
- [ ] 事实主张尽量附有可核查来源；
- [ ] 尚未核查的内容已明确标记；
- [ ] AI参与方式已经披露；
- [ ] 没有把多个模型的一致意见当作独立证据；
- [ ] 已选择正确的Discussion、Issue、评论或长期目录；
- [ ] 已说明需要的审查类型；
- [ ] 我已经审阅将被公开的最终内容。

# Pull Request要求

PR至少说明：

- 修改目的和主要变化；
- 关联Discussion和Issue；
- 数据分类和目标内容区；
- `source_language`和翻译状态；
- 是否修改规范、治理或兼容性；
- AI参与角色；
- 风险、限制和未解决问题；
- 需要哪类语言、领域、安全或治理审查；
- 起草者是否参与最终批准。

一个PR应聚焦一个可审查主题，不要混合多个无关重大议题。

# 正式审查和发布

普通非规范内容通常需要一名独立人类审查者。

正式规范、重大治理和高影响研究通常需要：

- 关联正式Proposal或治理依据；
- 至少两名人类审查；
- 至少一名审查者未参与起草；
- 重要异议被明确记录；
- 经过合理公开审查期；
- 由发布管理员检查后形成Release。

建议默认审查期：一般正式规范7天，重大治理修改14天。紧急安全修订可以临时执行，但必须尽快公开复核。

# 关闭Discussion或Issue

关闭时应说明：

- 关闭原因；
- 当前结果；
- 关键证据；
- 未解决异议；
- 后续Proposal、PR、Decision、Specification或Research链接；
- 状态是完成、拒绝、重复、暂缓还是超出范围。

一般观点争议不应通过删除历史解决。

# 研究结果

研究记录应尽量包括：

- 问题与假设；
- 方法；
- 数据来源和许可；
- 软件、模型和环境版本；
- 结果；
- 限制和不确定性；
- 复现步骤；
- 已知反例和异议；
- 预先定义的成功或失败标准；
- 人类与AI各自承担的工作。

# 安全问题

涉及未公开漏洞、个人数据、访问令牌或可能造成现实伤害的内容，请不要直接创建公开Discussion或Issue。参照 [`DATA_CLASSIFICATION.md`](DATA_CLASSIFICATION.md)、[`SECURITY.md`](SECURITY.md) 和 [`docs/threat-model.md`](docs/threat-model.md) 最小化披露，并联系维护者建立适当处理方式。
