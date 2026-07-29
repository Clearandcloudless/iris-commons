# 通过AI参与 Iris Commons

> 本文件既写给人类，也写给代表人类工作的AI助手。

Iris Commons 的目标是让参与者**不必先学习GitHub和项目文档**。完成一次连接或授权后，你可以继续使用自然语言，让AI帮助你理解项目、寻找讨论、整理观点、判断公开风险、提交Discussion或Issue、参与审查或准备Pull Request。

Iris Commons是可复制的GitHub与文档协议模板。使用本模板建立的项目彼此独立，不需要注册、互联、同步或向Iris Commons提交研究成果。

仓库地址：

```text
https://github.com/Clearandcloudless/iris-commons
```

## 最快开始：不安装任何工具

把下面的提示词发送给能够访问网页或GitHub的GPT、Gemini、Claude或其他AI：

```text
请阅读 https://github.com/Clearandcloudless/iris-commons ，优先读取：
AGENTS.md、AI_PARTICIPATION.md、DATA_CLASSIFICATION.md、
COMMUNICATION_PROTOCOL.md、CONTENT_LIFECYCLE.md、
TEAM_GOVERNANCE.md、LANGUAGE_POLICY.md、GOVERNANCE.md
以及当前开放Discussions、Issues和Pull Requests。

使用我正在使用的语言向我说明：
1. 这个项目试图解决什么问题；
2. 当前有哪些适合我参与的讨论、问题或审查；
3. 根据我的背景，哪一种贡献最有价值；
4. 我的内容属于D0、D1、D2还是D3；
5. 它应该进入Discussion、Issue、评论、Proposal、Research、Review还是其他位置；
6. 正式工作需要哪些人类角色、审查和批准。

不要要求我自己阅读GitHub文档。你负责检索、解释、查重和整理。
开放式交流优先进入Discussion；可追踪问题进入Issue；
普通想法不要直接创建仓库文件。
在创建任何公开Discussion、Issue、评论、分支、Review或Pull Request之前，
先向我展示最终内容、数据分类、目标位置和治理路径，并取得明确确认。
```

AI没有GitHub写权限时，也可以生成完整可复制的Discussion、Issue、评论、Review或PR草稿，再由你在GitHub网页中发布。

# 三种参与方式

## 方式A：AI阅读，用户提交

适合第一次参与或不愿授予GitHub权限的用户。

```text
AI读取公开仓库
  → 检查相关Discussion、Issue和现行规则
  → 与用户讨论
  → 将材料默认视为D1
  → 选择最小GitHub对象和治理路径
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
  → AI读取仓库、讨论、Issues和规范
  → 用户使用自然语言表达
  → AI分类、查重、选择目标对象和审查路径
  → AI生成公开草稿
  → 用户确认
  → AI创建Discussion、Issue、评论、Review或草稿PR
```

推荐使用OAuth或细粒度令牌，只授予完成任务所需的最低权限。

## 方式C：AI代理处理完整贡献流程

适合需要修改文档、协议、数据结构或代码的贡献者。

```text
Fork或克隆仓库
  → AI创建分支
  → 读取分类、交流、生命周期和治理规则
  → 修改正确目录中的文件
  → 检查差异、元数据、风险和审查要求
  → 用户审阅
  → AI提交并创建Pull Request
  → 独立人类Review
```

AI不得自动合并主分支、发布Release、决定优先级或正式批准内容，也不得在未确认时公开私人对话、本地文件或上传材料。

# 公开内容的三个判断

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

Discussion、Issue、评论、Draft PR、分支和名为`private/`的目录都属于公开空间。文件夹名称不能提供保密能力。

## 2. 应该使用哪种GitHub对象？

按照 [`COMMUNICATION_PROTOCOL.md`](COMMUNICATION_PROTOCOL.md)：

```text
开放交流、提问或寻找合作者 → Discussion
可追踪的问题、任务或争议   → Issue
证据、反例、回复或澄清     → Issue comment
正式长期修改               → branch + Pull Request
独立审查                   → Review
稳定版本                   → Decision / Spec / Result / Release
```

GitHub Discussions未启用时，可以使用带`type:discussion`标记的Issue临时代替。

## 3. 长期内容和治理应放在哪里？

按照 [`CONTENT_LIFECYCLE.md`](CONTENT_LIFECYCLE.md) 和 [`TEAM_GOVERNANCE.md`](TEAM_GOVERNANCE.md)：

```text
成熟正式提案             → proposals/ + branch + PR
结构化研究工作           → research/ + branch + PR
已接受决策及理由         → decisions/ + reviewed PR
当前规范性协议           → specs/ + reviewed PR
机器可读格式             → schemas/ + reviewed PR
非规范示例               → examples/ + PR
维护中的翻译             → translations/ 或README语言版本
撤回、替代或完成的材料   → archive/，且必须明确历史状态
```

正式工作还应识别：

- 谁负责问题分诊；
- 是否进入`Now / Next / Explore`；
- 是否需要正式立项和临时工作组；
- 需要哪类独立人类审查；
- 谁负责合并和发布；
- 是否存在利益冲突或申诉路径。

不要建立：

```text
users/<name>/ideas/
submissions/misc/
```

Discussion和Issue已经承担公开交流、作者归属、时间线和讨论功能。长期文件按主题和功能组织，而不是按用户组织。

# AI可以帮助承担的参与角色

参与者可以让AI协助自己承担不同贡献角色：

- **Participant**：提出问题、观点和经验；
- **Contributor**：提交证据、文本、代码或研究；
- **Challenger**：提出反例、异议和失败条件；
- **Reviewer**：审查内容、证据、方法、语言、安全、伦理、治理或实现；
- **Translator**：维护原文、译文和术语；
- **Synthesizer**：整理长讨论但保留分歧；
- **Reproducer**：复现研究或试验；
- **Steward**：协助分诊、路线、发布或程序复核。

AI是秘书和工具，不是委员会成员、正式投票者、维护者任命者或最终批准者。

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
5. 审阅diff、分类、目标目录、治理路径和PR内容后再公开提交。

推荐提示词：

```text
阅读AGENTS.md、DATA_CLASSIFICATION.md、COMMUNICATION_PROTOCOL.md、
CONTENT_LIFECYCLE.md、TEAM_GOVERNANCE.md和LANGUAGE_POLICY.md。

根据Issue #编号提出一个最小、可审查的修改方案。
先说明数据分类、生命周期状态、目标目录、负责人和所需审查类型。
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
读取GEMINI.md、AGENTS.md、DATA_CLASSIFICATION.md、
COMMUNICATION_PROTOCOL.md、CONTENT_LIFECYCLE.md
和TEAM_GOVERNANCE.md。

检查当前开放Discussions和Issues，用我的语言推荐一个适合参与的议题。
普通想法只生成Discussion或Issue草稿；成熟文件修改必须使用正确目录和PR。
正式工作说明所需人类审查和批准；只在我确认后公开写入。
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
先读取CLAUDE.md、AGENTS.md、DATA_CLASSIFICATION.md、
COMMUNICATION_PROTOCOL.md、CONTENT_LIFECYCLE.md
和TEAM_GOVERNANCE.md。

帮助我选择一个Discussion、Issue或Review任务并完成贡献。
不要把普通想法直接写成仓库文件。
正式修改说明负责人和审查要求。
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
按照仓库的Copilot instructions、DATA_CLASSIFICATION.md、
COMMUNICATION_PROTOCOL.md、CONTENT_LIFECYCLE.md
和TEAM_GOVERNANCE.md工作。

先总结当前Discussions、Issues和需要审查的PR，不要默认修改文件。
需要公开写入时，先展示内容、分类、目标位置、治理路径和diff并请求确认。
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

## 开始一场开放讨论

```text
我想讨论下面的问题：[使用自己的语言描述]。
请先搜索已有Discussion和Issue，判断它是否仍是开放交流，
还是已经形成可追踪的问题。
保留我的原始表达，区分事实、推断、观点和建议。
生成D0公开草稿，在我确认前不要提交。
```

## 提出一个明确问题或新想法

```text
我有下面这个问题或想法：[使用自己的语言描述]。
请先把它当作D1私人草稿，检查隐私、版权、事实和安全风险。
搜索是否已有类似Discussion、Issue或Proposal。
按照Iris Commons的Issue模板整理，但保留我的原始表达。
区分事实、推断、疑问和建议。
生成D0公开草稿，在我确认前不要提交，也不要创建仓库文件。
```

## 参与现有讨论

```text
读取Discussion或Issue #编号及全部评论。
用我的语言解释各方真正的分歧，不要只给多数意见。
帮助我形成一条有新信息、有证据、有明确反例或有审查价值的评论。
先完成D0检查并让我确认，再提交评论。
```

## 整理阶段性摘要

```text
总结Discussion或Issue #编号。
必须分别列出共同认识、主要分歧、各方依据、关键证据和反例、
尚未核查的信息、未解决问题和下一步。
不要把多数意见写成正式共识，不要删除重要异议。
标明AI起草和人类审阅状态。
```

## 将讨论升级为Proposal

```text
检查Issue #编号是否已经具备明确问题、具体方案、替代方案、
风险、验证标准、未解决问题、负责人和所需审查类型。

不成熟时继续使用Issue；不要为了整理方便创建文件。
成熟时生成proposals/IRIS-RFC-XXXX/proposal.md草稿，
加入来源Discussion和Issue、状态、语言、D0分类、治理和AI参与元数据，
通过分支和Pull Request提交，并在创建PR前让我审阅diff。
```

## 评估问题优先级

```text
读取TEAM_GOVERNANCE.md和当前问题池。
按照目标相关性、公共价值、紧迫性、可验证性、可执行性、
基础性影响和风险维护成本，生成带理由的建议。
不要仅按点赞、评论数量、语言或传播范围排序。
把结果标记为AI建议，不要自行修改正式Now / Next / Explore。
```

## 发起正式目标

```text
根据Issue #编号起草目标立项材料，包括问题、范围、非范围、
交付物、成功标准、负责人、审查者、依赖、时间盒和停止条件。
说明需要哪一级人类确认。
立项不代表预先接受最终结论，不要自行成立工作组或宣布生效。
```

## 提交研究结果

```text
根据CONTENT_LIFECYCLE.md判断内容应进入
research/questions、research/evidence、research/pilots
还是research/results。

说明方法、数据来源和许可、环境版本、预设成功标准、结果、
不确定性、限制、反例、复现状态、重要异议以及人类和AI各自的工作。
不要把D2受限数据或原始个人数据放入公共仓库。
```

## 进行正式Review

```text
读取PR #编号、来源Issue、相关规范和TEAM_GOVERNANCE.md。
说明我实际审查的维度：内容、证据、方法、语言、安全、伦理、
治理或实现。列出阻塞问题、非阻塞建议和未审查范围。
AI可以帮助分析，但最终Review必须由我审阅和确认。
```

## 修改正式规范

```text
读取当前specs、decisions、governance、相关Proposal
以及TEAM_GOVERNANCE.md。
确认本次修改具有已接受提案或治理依据。
说明兼容性、迁移影响、规范版本、公开审查期和所需独立审查者。
使用分支和Pull Request；不要自行宣布规范生效、合并主分支或发布Release。
```

## 查询历史内容

```text
依次检查当前specs和decisions、治理文件、活跃Proposal和Research、
Issues与PR、Discussions、archive、Git历史和Releases。
明确区分当前规则与历史材料，不要把archive内容当作现行规范。
```

# AI助手必须执行的工作流程

当AI收到“帮助我参与Iris Commons”或模板项目的类似请求时，应：

1. 读取`AGENTS.md`和相关项目规则；
2. 使用用户当前语言交流，不强迫用户改用英文；
3. 主动检索现有Discussion、Issue、Proposal、Research、Decision和Specification；
4. 将用户材料默认视为`D1 review-required`；
5. 阻止`D2`和`D3`内容进入公共仓库；
6. 保留原文，并区分译文、摘要、事实、推断、立场和建议；
7. 为公开内容选择最小合适GitHub对象和正确目录；
8. 开放交流优先使用Discussion，可追踪问题使用Issue；
9. 普通想法不自动升级为长期文件；
10. 对外部事实提供来源或明确标注尚未核查；
11. 在公开前检查个人信息、密钥、版权和现实安全风险；
12. 对正式工作识别负责人、审查维度、批准和发布路径；
13. 展示最终文本或diff、D0分类、目标位置和治理路径；
14. 取得明确确认后再执行GitHub写入；
15. 使用用户自己的GitHub身份并披露AI角色；
16. 写入失败时提供完整可复制草稿；
17. 不自动决定优先级、立项、正式接受或人员任命；
18. 不自动合并主分支、发布Release、修改治理或宣布规范生效。

# 权限底线

建议按以下顺序逐步授权：

```text
只读公开仓库
  → Discussions或Issues读写
  → Pull Requests和Reviews读写
  → 用户自己的Fork或授权分支内容写入
```

默认不要授予：

- 仓库删除；
- 管理员权限；
- Secrets读取；
- 工作流任意修改；
- 组织成员管理；
- 无限制访问全部私人仓库；
- 无人监督的主分支合并；
- 无人监督的Release发布；
- AI对正式优先级、立项、批准或任命的最终权力。

**Iris Commons希望消除的是参与门槛，而不是安全、治理和人的最终授权边界。**
