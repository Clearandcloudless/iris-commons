# Data Classification / 数据分类分级

Status: `draft-0.1`

本文件规定内容在进入 Iris Commons 公共仓库之前应如何分类。它解决的是：**一项内容是否允许公开，以及公开前需要什么处理。**

> GitHub 文件夹、分支和 Draft Pull Request 都不是保密边界。任何进入本公共仓库的内容都必须按公开信息处理。

## 1. Classification levels / 分类级别

| Level | Name | Meaning | Allowed destination |
|---|---|---|---|
| `D0` | `public-ready` | 已确认拥有公开权利，且完成必要的隐私、版权、事实与安全检查 | Public Issue, Comment, Pull Request, repository file or Release |
| `D1` | `review-required` | 可能包含个人信息、未经授权内容、事实风险、版权问题或语境不清 | Private AI draft, local file or other non-public review space only |
| `D2` | `restricted` | 仅限特定成员、机构或研究团队访问 | Separate private repository or controlled storage; never this public repository |
| `D3` | `prohibited` | 密钥、密码、访问令牌、未经授权个人数据、明显违法或高现实伤害材料 | Do not store or publish; remove, redact or use an approved secure process |

## 2. Default rule / 默认规则

用户与AI之间的原始对话、上传材料和初始草稿默认视为：

```yaml
classification: D1
classification_status: review-required
```

只有在满足以下条件后，内容才能转为 `D0`：

1. 用户明确选择并授权公开；
2. 已移除密钥、个人身份信息和未经授权材料；
3. 已检查第三方版权、许可和保密义务；
4. 已区分事实、推断、观点、建议和未核查主张；
5. 已考虑是否可能造成现实安全、伦理或隐私伤害；
6. 用户已审阅最终公开文本或清晰的差异摘要。

“AI可以读取”不等于“用户授权公开”。“用户曾经说过”也不等于“用户允许发布”。

## 3. Public repository boundary / 公共仓库边界

本仓库只允许保存 `D0 public-ready` 内容。

以下位置同样属于公开空间：

- Issues and Issue comments;
- Discussions;
- Pull Requests, including draft PRs;
- branches and commits;
- Git history;
- Releases and workflow artifacts exposed by the repository;
- files placed in folders named `private`, `internal`, `restricted` or similar.

不得通过目录名称制造虚假的保密感。

## 4. Typical classification examples / 常见示例

### Usually D0 after confirmation

- 已由作者确认公开的想法、问题和建议；
- 公开来源的文献摘要和引用；
- 已脱敏的案例；
- 开源代码、公开实验方法和可公开结果；
- 经审查的翻译、提案、决策和规范。

### Usually D1 until reviewed

- 私人AI对话摘录；
- 尚未核查的事实陈述；
- 可能含姓名、联系方式或机构内部信息的文本；
- 第三方提供但未确认许可的文件；
- AI自动生成的公开草稿；
- 原始访谈、截图、日志或数据样本。

### D2 examples

- 仅对研究团队开放的未脱敏数据；
- 受合同、伦理审批或机构政策限制的资料；
- 尚未公开的合作研究材料；
- 需要成员身份验证的内部审查记录。

### D3 examples

- passwords, API keys, access tokens and private keys;
- 未经授权的身份证件、生物识别或详细医疗数据；
- 可直接实施重大现实伤害的材料；
- 明确要求秘密保存且无公开授权的第三方内容。

## 5. AI classification workflow / AI分类工作流

AI在公开写入前必须：

```text
receive user content
  → assume D1
  → identify privacy, copyright, factual, ethical and safety risks
  → redact or restructure when possible
  → show the exact public version to the user
  → obtain explicit authorization
  → mark as D0
  → choose the correct GitHub destination
```

若内容属于 `D2` 或 `D3`，AI应停止公共写入，并解释为什么该内容不能进入本仓库。AI可以帮助生成不含敏感信息的公开摘要，但仍需用户确认。

## 6. Suggested metadata / 建议元数据

对于正式文件或结构化记录，可使用：

```yaml
publication:
  classification: D0
  authorized_by: github-login-or-role
  authorized_at: YYYY-MM-DD
  sensitive_data_reviewed: true
  third_party_rights_reviewed: true
  license: CC-BY-4.0
```

不得在公共元数据中写入私人对话ID、内部文件路径、访问令牌或不必要的个人信息。

## 7. Incident handling / 误公开处理

发现误公开的 `D1`、`D2` 或 `D3` 内容时：

1. 立即停止进一步传播和自动处理；
2. 通知维护者并按 `SECURITY.md` 处理；
3. 撤销或轮换已泄露凭证；
4. 根据风险删除或隐藏内容，但不要假定普通删除能够消除所有副本；
5. 记录不扩大伤害的纠正说明；
6. 检查Fork、缓存、构建产物和关联记录是否受到影响。

## 8. Relationship to lifecycle / 与生命周期的关系

数据分类与内容生命周期是两个独立维度：

- `DATA_CLASSIFICATION.md` 决定内容**能否公开**；
- `CONTENT_LIFECYCLE.md` 决定公开内容**当前处于什么阶段、应进入哪个目录**。

只有 `D0` 内容才能进入公共生命周期。