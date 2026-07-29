# Contributing / 参与指南

感谢参与 Iris Commons。任何语言、专业背景和GitHub经验水平的参与者都可以贡献。

你不需要先阅读整个仓库，也不需要先学会Issue、分支或Pull Request。可以先把仓库地址交给你的AI，让它读取 [`AI_PARTICIPATION.md`](AI_PARTICIPATION.md) 并负责解释与GitHub操作。

## 最简单的参与方式

向你的AI发送：

```text
阅读 https://github.com/Clearandcloudless/iris-commons 的AI_PARTICIPATION.md和AGENTS.md。
检查当前开放Issues，根据我的背景和语言推荐一个适合参与的议题。
你负责GitHub流程，但任何公开提交前必须向我展示最终内容并取得确认。
```

完整接入方法见 [`AI_PARTICIPATION.md`](AI_PARTICIPATION.md)。

## 可以贡献什么

- 提出项目构想中的漏洞、失败条件或反例；
- 分享真实的跨语言、跨文化或跨专业交流障碍；
- 研究同类项目、开放标准和现有平台；
- 改进AI秘书协议、治理、数据模型和安全边界；
- 提交适合作为试验的公益研究课题；
- 翻译内容并指出无法准确转换的概念；
- 核查引用、复现实验或挑战已有结论；
- 编写原型、自动检查和跨平台适配工具。

## 选择提交类型

### Issue

适合：

- 新问题、想法或假设；
- 对现有设计的批评；
- 风险、遗漏和反例；
- 公益试验课题；
- 在形成正式修改前收集意见。

### Issue comment

适合：

- 补充证据、案例或资料；
- 解释术语和语言语境；
- 提出明确反对意见；
- 回答现有问题；
- 报告复现或验证结果。

### Pull Request

适合：

- 修改项目文档；
- 增加或调整协议；
- 提交完整提案或研究结果；
- 修改Schema、自动检查或原型代码；
- 修订翻译版本。

大型修改应先创建Issue。没有仓库写权限的参与者应使用Fork和Pull Request。

## 语言规则

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

建议正式跨语言提交包含：

```yaml
source_language: zh-CN
bridge_summary_language: en
translation_method: ai
translation_status: machine-generated
human_reviewed: true
```

## 保留原始表达

AI可以帮助整理，但不要只提交经过AI重写的文本。对于重要观点，建议保留：

```markdown
## Original / 原文

参与者最初表达。

## Structured proposal / 结构化提案

AI或人类整理后的版本。

## Translation notes / 翻译说明

语义差异、术语和不确定性。
```

短评论不必机械使用全部结构，但不得把AI改写冒充原作者原话。

## AI辅助披露

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

## 公开前确认

任何AI工具在创建Issue、评论、分支、commit或Pull Request之前，都应：

1. 向参与者展示最终公开文本或清晰的diff摘要；
2. 指出隐私、版权、事实和安全风险；
3. 取得明确确认；
4. 仅使用完成任务所需的最低权限；
5. 公开后返回链接和实际操作结果。

如果AI没有写权限，应提供完整的可复制草稿，不得要求参与者重新整理。

## 提交前检查

- [ ] 内容属于我有权公开的范围；
- [ ] 已移除个人信息、密钥和敏感数据；
- [ ] 原始语言和必要的语言标识已经保留；
- [ ] 原文、译文、摘要、推断和建议没有混为一体；
- [ ] 事实主张尽量附有可核查来源；
- [ ] 尚未核查的内容已明确标记；
- [ ] AI参与方式已经披露；
- [ ] 没有把多个模型的一致意见当作独立证据；
- [ ] 第三方材料和数据许可已经说明；
- [ ] 我已经审阅将被公开的最终内容。

## 高价值的批评

请批评主张、证据、方法和系统，而不是攻击参与者。高价值反对意见通常说明：

1. 反对的具体主张；
2. 推理漏洞、证据或反例；
3. 可能造成的现实影响；
4. 原主张在什么条件下仍可能成立；
5. 如何修改、实验或验证。

## Pull Request要求

PR至少说明：

- 修改目的和主要变化；
- 关联Issue；
- `source_language`和翻译状态；
- 是否修改规范内容；
- AI参与角色；
- 风险、限制和未解决问题；
- 需要哪类语言、领域、安全或治理审查。

一个PR应聚焦一个可审查主题，不要混合多个无关重大议题。

## 研究结果

研究记录应尽量包括：

- 问题与假设；
- 方法；
- 数据来源和许可；
- 软件、模型和环境版本；
- 结果；
- 限制和不确定性；
- 复现步骤；
- 已知反例和异议；
- 人类与AI各自承担的工作。

## 安全问题

涉及未公开漏洞、个人数据、访问令牌或可能造成现实伤害的内容，请不要直接创建公开Issue。参照 [`SECURITY.md`](SECURITY.md) 和 [`docs/threat-model.md`](docs/threat-model.md) 最小化披露，并联系维护者建立适当处理方式。