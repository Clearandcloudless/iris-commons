# Communication Protocol / 交流协议

Status: `draft-0.1`

本文件定义一个独立项目如何仅依赖GitHub、Markdown文档和参与者自选AI，完成从自由表达、结构化讨论到正式知识发布的全过程。

> Iris Commons提供的是可复制的协作模板与文档协议。复制后形成的项目彼此独立，不需要注册、互联、同步研究内容或服从Iris Commons的治理。

## 1. 适用范围

本协议适用于使用Iris Commons模板建立的独立公开项目，包括但不限于公共研究、开放知识、公益设计、技术规范、教育协作和跨语言议题讨论。

项目可以修改本协议，但应公开说明：

- 哪些规则被保留、删除或替换；
- 当前规则的版本和生效时间；
- 谁拥有审查、批准和合并权限；
- 参与者如何提出异议或申诉。

## 2. GitHub对象分工

不同GitHub对象承担不同交流职能。不要让Issue同时承担闲聊、投稿、任务、论文和最终决策的全部功能。

| Object | Primary purpose | Typical content |
|---|---|---|
| Discussion | 开放交流和问题发现 | 提问、初步想法、寻找合作者、资料分享、项目元讨论 |
| Issue | 需要持续追踪的结构化对象 | 问题、假设、争议、风险、任务、研究课题、提案前置讨论 |
| Issue comment | 对现有议题的聚焦贡献 | 证据、反例、澄清、替代方案、风险、复现报告、正式异议 |
| Branch + Pull Request | 对长期公共知识的正式修改 | 提案、研究结果、规范、决定、Schema、翻译、代码和治理文件 |
| Review | 独立审查 | 内容、证据、方法、语言、安全、伦理、治理和实现审查 |
| Decision / Specification / Result | 经过审查的长期记录 | 已接受决定、当前规范、可复现结果及其限制 |
| Release | 某一时间点的稳定快照 | 版本说明、兼容性、已知争议、废弃和迁移信息 |

GitHub Discussions未启用时，可以用带有`type:discussion`标签的Issue临时代替，但应明确其非任务性质和退出条件。

## 3. 标准交流流程

```text
private draft (D1)
        │ human review and authorization
        ▼
open conversation
Discussion
        │ a trackable question, task or dispute emerges
        ▼
structured issue
Issue + focused comments
        │ evidence, critique, translation and synthesis
        ▼
formal work
Proposal / Research / Specification draft
        │ branch + Pull Request + independent review
        ▼
human decision
accepted / rejected / disputed / returned for revision
        │
        ▼
long-lived record
Decision / Specification / Research Result / Release
        │ new evidence or failure
        ▼
revised / superseded / withdrawn / reopened
```

项目可以跳过不必要的阶段，但不得跳过数据分类、公开授权和重大内容的独立人类审查。

## 4. 从Discussion升级为Issue

Discussion适合开放交流。出现以下情况之一时，应建立或关联Issue：

- 已形成可以明确描述的问题；
- 需要跟踪责任人、依赖、里程碑或验证结果；
- 出现需要正式回应的重要争议；
- 已有足够材料形成研究问题或工作目标；
- 需要修改长期文件、协议、Schema或代码。

升级时应保留原Discussion链接，并说明：

- 问题是什么；
- 已知背景和主要观点；
- 尚缺哪些证据；
- 预期下一步；
- 哪些分歧尚未解决。

不要由AI在无人审阅时自动关闭原Discussion或宣布已经形成共识。

## 5. Issue中的贡献类型

参与者可以使用自然语言表达，不要求掌握格式。AI秘书可以帮助整理为下列贡献类型：

```text
[Evidence]       证据、资料或案例
[Counterexample] 反例或失败条件
[Question]       澄清请求
[Interpretation] 对事实的解释
[Alternative]    替代方案
[Risk]           隐私、安全、伦理、法律或维护风险
[Translation]    翻译和语义说明
[Reproduction]   复现、部分复现或复现失败
[Objection]      需要被正式记录的异议
[Summary]        保留分歧的阶段性总结
```

前缀是可选辅助，不得成为参与门槛。

## 6. 区分事实、推断、观点和建议

正式贡献应尽量区分：

```text
Observation / Fact   观察到什么，来源是什么
Inference            如何解释事实，存在哪些不确定性
Position             参与者当前持有什么判断
Proposal             建议项目采取什么行动
```

AI不得把推断改写为已验证事实，也不得把阶段性多数意见写成项目最终立场。

## 7. 阶段性摘要

长讨论可以由人类或AI起草阶段性摘要。摘要至少应包含：

- 当前共同认可的内容；
- 主要分歧及各方依据；
- 已提交的关键证据和反例；
- 尚未核查或缺失的信息；
- 未解决问题；
- 可执行的下一步；
- 原始讨论链接；
- 摘要起草者、AI参与方式和人类审阅状态。

摘要不得删除重要异议，不得仅以“大家基本同意”代替真实讨论结构。参与者可以要求修正遗漏或失真的摘要。

## 8. 问题状态和关闭规则

建议使用以下知识状态：

```text
idea → discussing → proposed → under-review → accepted
                                      ├→ rejected
                                      └→ withdrawn
accepted → implemented / reproduced / validated
accepted → disputed → revised / superseded / withdrawn
```

关闭Issue时必须说明：

- 关闭原因；
- 当前结论或处理结果；
- 关键证据；
- 是否仍有未解决异议；
- 后续Proposal、PR、Decision、Specification或Research链接；
- 状态是完成、拒绝、重复、暂缓还是超出范围。

一般观点争议不应通过删除历史解决。

## 9. Pull Request和Review

PR是长期公共知识变更的正式入口。PR至少应说明：

- 修改目标和范围；
- 来源Issue或Discussion；
- 数据分类；
- 内容生命周期位置；
- 是否改变规范、治理或兼容性；
- AI承担的角色；
- 已知风险、限制和未解决问题；
- 需要的审查类型。

审查维度可以包括：

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

一个审查者只需要对自己实际审查的维度负责。重大内容不得由起草者作为唯一批准者。

## 10. 定期交流记录

独立项目可以建立以下GitHub原生日常节奏：

### Weekly digest

- 新增议题；
- 新证据和反例；
- 重要异议；
- 进入PR的内容；
- 已接受、撤回或替代的内容；
- 需要帮助的任务；
- 适合新参与者的贡献入口。

### Milestone or version review

- 当前目标进度；
- 阻塞和依赖；
- 问题清单变化；
- 需要立项、暂停或终止的工作；
- 下一个周期的`Now / Next / Explore`。

### Release notes

- 本版本正式包含什么；
- 哪些内容仍存在争议；
- 哪些内容已废弃或被替代；
- 兼容性和迁移影响；
- 人类与AI各自承担的工作。

AI可以起草这些记录，但发布前必须由人类审阅。

## 11. AI在交流中的职责

AI可以：

- 解释项目规则和GitHub对象；
- 搜索相关Discussion、Issue、Proposal和Specification；
- 帮助查重、分类和路由；
- 整理自然语言表达；
- 翻译并标记语义不确定性；
- 生成保留异议的摘要；
- 草拟Issue、评论、PR和Review；
- 建议审查维度和下一步；
- 在明确授权后执行有限GitHub写入。

AI不能：

- 代表参与者发表未经确认的公共立场；
- 自动宣布形成共识；
- 独立拒绝、关闭或降低重大议题优先级；
- 作为唯一审查者或最终批准者；
- 把多个模型的一致结论当作独立证据；
- 自动合并主分支、发布Release或修改治理；
- 删除重要异议以获得更简洁的结论。

## 12. 模板独立性

使用本模板建立的新项目：

- 拥有独立名称、范围、治理、维护者和知识库；
- 不需要向Iris Commons注册；
- 不需要与其他复制项目互联或同步；
- 不需要向Iris Commons提交研究成果；
- 可以自由修改模板，只需对本项目参与者公开当前规则；
- 可以自愿将具有通用价值的模板改进反馈给Iris Commons。

Iris Commons维护的是一种可复制的人类—AI协作方法，而不是所有复制项目的中央知识库或管理机构。
