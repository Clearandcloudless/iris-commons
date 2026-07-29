# 研究记录模型草案

状态：`draft-0.1`

Iris Commons 需要一种同时适合人类阅读和机器处理的最小记录格式，用于连接问题、观点、证据、翻译、实验和决策。

## 设计目标

- 保留原始语言和作者意图；
- 区分事实、观点、推断和结论；
- 记录AI参与但不强迫公开私人提示词；
- 支持一个记录存在多个翻译和修订；
- 能从GitHub迁移到其他平台；
- 对小项目足够简单，对复杂项目可扩展。

## 建议记录类型

- `question`：研究问题；
- `idea`：初步想法；
- `claim`：可争论主张；
- `evidence`：支持或反对材料；
- `hypothesis`：可验证假设；
- `method`：方法或实验设计；
- `result`：实验或分析结果；
- `critique`：反例、限制或质疑；
- `translation`：派生译文；
- `decision`：项目决策；
- `summary`：讨论摘要；
- `retraction`：撤回或纠错记录。

## 最小YAML示例

```yaml
iris_record: "0.1"
id: "claim-2026-0001"
type: claim
title: "示例主张"
status: discussing

content:
  language: zh-CN
  text: |
    这里保存原始主张。
  original: true

authorship:
  human_contributors:
    - github: example-user
      role: author
  ai_assistance:
    used: true
    provider: OpenAI
    model: unknown
    roles: [drafting]
    human_reviewed: true

provenance:
  created_at: "2026-07-29T00:00:00Z"
  source_type: human-ai-conversation
  source_reference: null

relations:
  supports: []
  contradicts: []
  translates: null
  derived_from: []
  related_issues: []

verification:
  level: unverified
  methods: []
  reviewers: []

license:
  content: CC-BY-4.0
  third_party_material: false
```

## 状态字段

推荐值：

- `idea`
- `discussing`
- `proposed`
- `reviewed`
- `accepted`
- `rejected`
- `reproduced`
- `validated`
- `disputed`
- `withdrawn`

状态变化必须由提交历史或关联决策解释。

## 原文与译文

译文应是独立记录，通过关系字段指向原文：

```yaml
type: translation
content:
  language: en
  original: false
relations:
  translates: "claim-2026-0001"
translation:
  method: machine
  provider: Google
  model: unknown
  reviewed_by_original_author: false
```

不得用译文覆盖原文。对关键文本，可以记录：

- 逐字翻译；
- 面向普通读者的意译；
- 术语说明；
- 原作者确认状态。

## 证据关系

证据记录至少说明：

- 支持还是反对哪个主张；
- 来源类型；
- 可访问位置；
- 获取日期；
- 许可证或使用限制；
- 是否为一手资料；
- 是否由独立参与者复核。

示例：

```yaml
type: evidence
relations:
  supports: ["claim-2026-0001"]
evidence:
  direction: support
  source_kind: primary-paper
  locator: "DOI or stable identifier"
  accessed_at: "2026-07-29"
  independently_checked: false
```

## 验证等级

建议使用描述性等级，而不是模型置信百分比：

- `unverified`：尚未核查；
- `source-checked`：来源存在且被正确引用；
- `method-reviewed`：方法经过审查；
- `independently-reproduced`：独立复现；
- `domain-validated`：满足该领域明确验证标准；
- `contested`：存在重要冲突证据。

模型给出的“90%置信度”不得自动映射为验证等级。

## 文件组织建议

小型项目可以使用：

```text
research/
├── questions/
├── claims/
├── evidence/
├── experiments/
├── translations/
└── decisions/
```

记录正文可以使用Markdown，YAML元数据置于front matter：

```markdown
---
iris_record: "0.1"
id: question-2026-0001
type: question
language: zh-CN
status: discussing
---

# 问题标题

正文……
```

## 待讨论问题

1. 是否需要全局唯一ID，还是仓库内唯一即可？
2. 人类身份如何在隐私与可归属之间平衡？
3. 模型版本未知时如何记录？
4. 如何表示一个观点由多人和多个AI共同演化？
5. 翻译修改是否需要原作者批准？
6. 哪些字段应强制，哪些应由领域扩展？
7. 如何与RO-Crate、PROV-O、DataCite等现有标准兼容？
