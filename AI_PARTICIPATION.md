# 通过AI参与 Iris Commons

> 本文件既写给人类，也写给代表人类工作的AI助手。

Iris Commons 的目标是让参与者**不必先学习GitHub和项目文档**。完成一次连接或授权后，你可以继续使用自然语言，让AI帮助你理解项目、寻找议题、整理观点、判断公开风险、提交Issue、参与讨论或准备Pull Request。

仓库地址：

```text
https://github.com/Clearandcloudless/iris-commons
```

## 最快开始：不安装任何工具

把下面的提示词发送给能够访问网页或GitHub的GPT、Gemini、Claude或其他AI：

```text
请阅读 https://github.com/Clearandcloudless/iris-commons ，优先读取：
AGENTS.md、AI_PARTICIPATION.md、DATA_CLASSIFICATION.md、
CONTENT_LIFECYCLE.md、LANGUAGE_POLICY.md、GOVERNANCE.md
以及当前开放Issues。

使用我正在使用的语言向我说明：
1. 这个项目试图解决什么问题；
2. 当前有哪些适合我参与的讨论；
3. 根据我的背景，哪一种贡献最有价值；
4. 我的内容属于D0、D1、D2还是D3；
5. 它应该进入Issue、评论、Proposal、Research还是其他位置。

不要要求我自己阅读GitHub文档。你负责检索、解释、查重和整理。
普通想法先进入Issue，不要直接创建仓库文件。
在创建任何公开Issue、评论、分支或Pull Request之前，
先向我展示最终内容、数据分类和目标位置，并取得明确确认。
```

AI没有GitHub写权限时，也可以生成完整可复制的Issue、评论或PR草稿，再由你在GitHub网页中发布。

# 三种参与方式

## 方式A：AI阅读，用户提交

适合第一次参与或不愿授予GitHub权限的用户。

```text
AI读取公开仓库
  → 检查相关Issue和现行规则
  → 与用户讨论
  → 将材料默认视为D1
  → 生成D0公开草稿
  → 用户确认
  → 用户在GitHub网页发布
```

优点：零配置、权限最小。  
限制：最后一步仍需用户打开GitHub。

## 方式B：AI连接GitHub，确认后代为提交

适合希望长期参与但不想学习GitHub操作的用户。

```text
一次授权GitHub
  → AI读取仓库、Issues和规范
  → 用户使用自然语言表达
  → AI分类、查重和选择目标位置
  → AI生成公开草稿
  → 用户确认
  → AI创建Issue、评论或草稿PR
```

推荐使用OAuth或细粒度令牌，只授予完成任务所需的最低权限。

## 方式C：AI代理处理完整贡献流程

适合需要修改文档、协议、数据结构或代码的贡献者。

```text
Fork或克隆仓库
  → AI创建分支
  → 读取分类和生命周期规则
  → 修改正确目录中的文件
  → 检查差异、元数据和风险
  → 用户审阅
  → AI提交并创建Pull Request
```

AI不得自动合并主分支，也不得在未确认时公开私人对话、本地文件或上传材料。

# 公开内容的两个判断

AI在执行任何GitHub写操作前，必须依次回答：

## 1. 这项内容能否公开？

按照 [`DATA_CLASSIFICATION.md`](DATA_CLASSIFICATION.md)：

| Level | Meaning | Public GitHub |
|---|---|---|
| `D0 public-ready` | 已确认可公开 | Allowed |
| `D1 review-required` | 仍需隐私、版权、事实或安全审查 | Not yet allowed |
| `D2 restricted` | 仅限特定团队或机构 | Not allowed |
| `D3 prohibited` | 密钥、未经授权个人数据或重大伤害材料 | Never allowed |

用户与AI的原始对话、上传材料和生成草稿默认是`D1`。只有用户审阅最终公开版本并明确授权后，内容才能转为`D0`。

Issue、评论、Draft PR、分支和名为`private/`的目录都属于公开空间。文件夹名称不能提供保密能力。

## 2. 公开后应该放在哪里？

按照 [`CONTENT_LIFECYCLE.md`](CONTENT_LIFECYCLE.md)：

```text
新想法、问题或假设       → Issue
具体证据、回复或反例     → Issue comment
成熟正式提案             → proposals/ + branch + PR
结构化研究工作           → research/ + branch + PR
已接受决策及理由         → decisions/ + reviewed PR
当前规范性协议           → specs/ + reviewed PR
机器可读格式             → schemas/ + reviewed PR
非规范示例               → examples/ + PR
维护中的翻译             → translations/ 或README语言版本
撤回、替代或完成的材料   → archive/，且必须明确历史状态
```

不要建立：

```text
users/<name>/ideas/
submissions/misc/
```

GitHub Issue已经承担公开投稿、作者归属、时间线和讨论功能。长期文件按主题和功能组织，而不是按用户组织。

# 主流AI接入方式

产品界面和套餐可能变化。无法使用某项写入集成时，始终可以退回“AI阅读、用户提交”方式。

## ChatGPT

### ChatGPT GitHub应用：适合阅读、理解和寻找议题

1. 打开ChatGPT的 **Settings / 设置 → Apps / 应用**；
2. 找到GitHub并完成授权；
3. 只选择确实需要访问的仓库；
4. 在对话中粘贴本文件顶部的“最快开始”提示词。

没有GitHub写入工具时，让ChatGPT生成最终文本，再由你提交。

官方说明：<https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt>

### Codex：适合修改仓库并创建Pull Request

1. 在Codex中连接GitHub；
2. 选择或创建与`iris-commons`相关的环境；
3. 让Codex先读取`AGENTS.md`和本文件；
4. 使用Ask模式理解议题，使用可修改仓库的模式准备变更；
5. 审阅diff、分类、目标目录和PR内容后再公开提交。

推荐提示词：

```text
阅读AGENTS.md、DATA_CLASSIFICATION.md、CONTENT_LIFECYCLE.md
和LANGUAGE_POLICY.md。

根据Issue #编号提出一个最小、可审查的修改方案。
先说明数据分类、生命周期状态和目标目录。
使用分支和Pull Request，不要直接修改受保护主分支。
保留原作者语言，并披露AI参与方式。
在创建PR前向我展示diff摘要和公开文本。
```

官方说明：<https://help.openai.com/en/articles/11369540-getting-started-with-codex>

## Gemini

### 普通Gemini对话

将仓库URL和“最快开始”提示词交给Gemini。若当前界面只能读取网页，让Gemini生成可提交草稿即可。

### Gemini CLI + GitHub MCP

Gemini CLI可以通过MCP连接GitHub工具。配置后发送：

```text
读取GEMINI.md、AGENTS.md、DATA_CLASSIFICATION.md
和CONTENT_LIFECYCLE.md。

检查当前开放Issues，用我的语言推荐一个适合参与的议题。
普通想法只生成Issue草稿；成熟文件修改必须使用正确目录和PR。
只在我确认最终内容、分类和目标位置后公开写入。
```

安全建议：

- 优先使用OAuth；
- 使用令牌时选择fine-grained PAT；
- 仅读取公开内容时不要授予写权限；
- 参与讨论通常只需要仓库读取和Issues读写；
- 创建PR时才增加Pull Requests及必要的Contents权限；
- 不要把令牌写进仓库或提示词。

官方说明：

- <https://geminicli.com/docs/cli/tutorials/mcp-setup/>
- <https://geminicli.com/docs/tools/mcp-server/>

## Claude

### Claude网页或桌面对话

直接提供仓库URL和“最快开始”提示词。没有GitHub写入权限时，让Claude准备完整提交内容。

### Claude Code

```bash
gh auth login
gh repo fork Clearandcloudless/iris-commons --clone
cd iris-commons
claude
```

进入Claude Code后发送：

```text
先读取CLAUDE.md、AGENTS.md、DATA_CLASSIFICATION.md
和CONTENT_LIFECYCLE.md。

帮助我选择一个Issue并完成贡献。
不要把普通想法直接写成仓库文件。
任何公开提交前先展示最终文本、diff、分类和目标位置；不要自动合并。
```

官方说明：

- <https://docs.anthropic.com/en/docs/claude-code/getting-started>
- <https://docs.anthropic.com/en/docs/mcp>

## GitHub Copilot / VS Code

1. 安装或连接GitHub MCP Server；
2. 通过OAuth登录；
3. 在Copilot Chat中选择Agent模式；
4. 让代理读取`.github/copilot-instructions.md`和本文件。

推荐提示词：

```text
按照仓库的Copilot instructions、DATA_CLASSIFICATION.md
和CONTENT_LIFECYCLE.md工作。

先总结当前Issues并询问我的兴趣，不要默认修改文件。
需要公开写入时，先展示内容、分类、目标位置和diff并请求确认。
```

官方说明：<https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/set-up-the-github-mcp-server>

## 其他MCP兼容AI或本地模型

GitHub远程MCP服务器地址：

```text
https://api.githubcopilot.com/mcp/
```

只启用必要工具集：

```text
repos
issues
pull_requests
```

不要默认授予Actions、Secrets、组织管理、仓库删除或全部私人仓库访问权限。

# 你可以直接对AI说什么

## 提出一个新想法

```text
我有下面这个想法：[使用自己的语言描述]。
请先把它当作D1私人草稿，检查隐私、版权、事实和安全风险。
搜索是否已有类似Issue。
按照Iris Commons的Issue模板整理，但保留我的原始表达。
区分事实、推断、疑问和建议。
生成D0公开草稿，在我确认前不要提交，也不要创建仓库文件。
```

## 参与现有讨论

```text
读取Issue #编号及全部评论。
用我的语言解释各方真正的分歧，不要只给多数意见。
帮助我形成一条有新信息、有证据或有明确反例的评论。
先完成D0检查并让我确认，再提交评论。
```

## 将讨论升级为Proposal

```text
检查Issue #编号是否已经具备明确问题、具体方案、替代方案、
风险、验证标准和未解决问题。

不成熟时继续使用Issue；不要为了整理方便创建文件。
成熟时生成proposals/IRIS-RFC-XXXX/proposal.md草稿，
加入来源Issue、状态、语言、D0分类和AI参与元数据，
通过分支和Pull Request提交，并在创建PR前让我审阅diff。
```

## 提交研究结果

```text
根据CONTENT_LIFECYCLE.md判断内容应进入
research/questions、research/evidence、research/pilots
还是research/results。

说明方法、数据来源和许可、环境版本、结果、不确定性、
限制、反例、复现状态以及人类和AI各自的工作。
不要把D2受限数据或原始个人数据放入公共仓库。
```

## 修改正式规范

```text
读取当前specs、decisions、governance和相关Proposal。
确认本次修改具有已接受提案或治理依据。
说明兼容性、迁移影响和规范版本。
使用分支和Pull Request；不要自行宣布规范生效或合并主分支。
```

## 查询历史内容

```text
依次检查当前specs和decisions、治理文件、活跃Proposal和Research、
Issues与PR、archive、Git历史和Releases。
明确区分当前规则与历史材料，不要把archive内容当作现行规范。
```

# AI助手必须执行的工作流程

当AI收到“帮助我参与Iris Commons”之类的请求时，应：

1. 读取`AGENTS.md`和相关项目规则；
2. 使用用户当前语言交流，不强迫用户改用英文；
3. 主动检索现有Issue、Proposal、Research和Specification；
4. 将用户材料默认视为`D1 review-required`；
5. 阻止`D2`和`D3`内容进入公共仓库；
6. 保留原文，并区分译文、摘要、推断和建议；
7. 为公开内容选择最小合适对象和正确目录；
8. 普通想法先进入Issue，不自动升级为长期文件；
9. 对外部事实提供来源或明确标注尚未核查；
10. 在公开前检查个人信息、密钥、版权和现实安全风险；
11. 展示最终文本或diff、D0分类和目标位置；
12. 取得明确确认后再执行GitHub写入；
13. 使用用户自己的GitHub身份并披露AI角色；
14. 写入失败时提供完整可复制草稿；
15. 不自动合并主分支、发布Release、修改治理或宣布规范生效。

# 权限底线

建议按以下顺序逐步授权：

```text
只读公开仓库
  → Issues读写
  → Pull Requests读写
  → 用户自己的Fork内容写入
```

默认不要授予：

- 仓库删除；
- 管理员权限；
- Secrets读取；
- 工作流任意修改；
- 组织成员管理；
- 无限制访问全部私人仓库；
- 无人监督的主分支合并。

**Iris Commons希望消除的是参与门槛，而不是安全边界。**