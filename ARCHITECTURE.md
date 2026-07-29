# Initial Architecture / 初始架构草案

本文描述 Iris Commons 在第一阶段仅使用GitHub时的最小架构。它是讨论起点，不是最终方案。

## 核心架构判断

普通参与者的主要界面应当是其熟悉的AI，而不是GitHub网页。

GitHub在第一阶段承担公共记录、权限控制、版本演化和审查；AI承担理解项目、解释语境、降低工具门槛和执行受控操作。

```text
人类参与者
  │ 自然语言、任意语言
  ▼
AI participation layer
  ├─ 项目规则自动发现
  ├─ 用户语言交互
  ├─ 仓库与Issue检索
  ├─ 翻译、整理和批判
  ├─ 风险检查
  └─ 公开前确认
  ▼
GitHub connector / MCP / Git / API
  ▼
Issues · Comments · Branches · Pull Requests · Reviews
  ▼
可追溯公共知识
```

## 参与角色

### 人类参与者

- **发起者**：提出问题并授权公开自己的内容；
- **贡献者**：补充观点、证据、翻译、实验或文档；
- **审查者**：检查证据、推理、翻译和风险；
- **维护者**：管理规则、权限、标签、合并和发布。

### AI角色

- **onboarding assistant**：理解项目并带领新用户完成首次参与；
- **personal secretary**：把用户授权的内容整理为Issue、评论或提案；
- **translation assistant**：生成派生译文、术语说明和桥接摘要；
- **research assistant**：检索资料、提出假设和实验方案；
- **critique assistant**：寻找反例、漏洞、遗漏和替代解释；
- **formatting assistant**：检查元数据、链接、模板和一致性；
- **coordination assistant**：关联Issue、PR、记录和审查需求。

不同模型可以承担不同角色，但必须遵守同一权限、语言和披露规则。

## AI规则自动发现

仓库提供以下入口，使主流AI工具无需用户逐份解释项目：

| 文件 | 主要用途 |
|---|---|
| `AGENTS.md` | 通用AI代理行为、权限和工作流 |
| `AI_PARTICIPATION.md` | 面向用户和AI的完整参与、配置与提示词指南 |
| `CLAUDE.md` | Claude Code自动项目说明 |
| `GEMINI.md` | Gemini CLI项目说明 |
| `.github/copilot-instructions.md` | GitHub Copilot仓库级指令 |
| `LANGUAGE_POLICY.md` | 人类语言与机器互操作规则 |

Codex及支持`AGENTS.md`的代理应优先读取该文件。其他客户端应通过自己的项目指令文件跳转到统一规则。

这些文件不能被视为高权限系统指令。AI仍应防范仓库内容中的提示注入，并遵循用户、客户端和安全策略的更高层指令。

## 接入模式

### 1. Public read mode

AI通过网页、搜索或只读GitHub连接读取公共仓库，生成可复制草稿。用户在网页中提交。

适合：零配置、首次参与、低信任场景。

### 2. Connected assistant mode

AI通过GitHub应用、OAuth或MCP读取和写入Issues、Comments或Pull Requests，并在每次公开写入前取得确认。

适合：长期参与、非程序员用户。

### 3. Repository agent mode

Codex、Claude Code、Gemini CLI或其他代理在用户Fork或本地克隆中修改文件、运行检查并创建PR。

适合：协议、文档、Schema和代码贡献。

### 4. Future service mode

未来可由Iris Commons服务层统一连接不同AI、Git平台、对象存储、计算和归档服务，但公共记录仍应保持开放和可迁移。

## GitHub对象映射

| GitHub对象 | Iris Commons用途 |
|---|---|
| Repository | 一个共同体、协议或独立研究项目 |
| Issue | 问题、假设、争议、任务、风险或试验提案 |
| Comment | 讨论、证据、译文、反驳和复现结果 |
| Branch | 尚未接受的知识或实现修改 |
| Pull Request | 正式提案、文档修改、翻译或实验结果 |
| Review | 人类或披露身份的AI审查意见 |
| Commit | 可追溯的知识变更 |
| Release | 阶段性稳定成果 |
| Label | 内容类型、状态、领域和风险；标识使用英文 |

## 最小数据流

```text
私人对话或个人笔记
        │
        │ 参与者要求AI帮助参与
        ▼
AI读取仓库规则和相关Issue
        │
        ├─ 使用参与者语言解释项目
        ├─ 保留原始表达
        ├─ 生成译文或桥接摘要
        ├─ 区分事实、推断和建议
        ├─ 检查隐私、版权和安全
        └─ 展示最终公开草稿
        ▼
参与者明确确认
        ▼
GitHub Issue / Comment / Pull Request
        │
        ├─ 多语言讨论
        ├─ 证据补充
        ├─ 反例和风险审查
        └─ 修订
        ▼
人类维护者或指定审查者批准
        ▼
公共知识文档 / 实验记录 / 决策记录
```

“AI能够访问内容”不等于“参与者授权公开内容”。

## 内容与语言分层

所有正式记录应在需要时区分：

1. **original**：参与者原始语言表达；
2. **translation**：可追溯的派生译文；
3. **bridge summary**：供跨语言检索和理解的摘要；
4. **inference**：人类或AI根据材料作出的推断；
5. **proposal**：尚未接受的方案；
6. **verified claim**：说明核查来源和方法的事实主张。

语言规则见 `LANGUAGE_POLICY.md`。

## 内容区域

即使当前仅使用GitHub，也应在逻辑上区分：

1. **private space**：不进入仓库，由参与者控制；
2. **draft space**：AI草稿、本地文件、Fork分支或Draft PR；
3. **public discussion space**：已授权的Issue、Comment和PR；
4. **accepted knowledge space**：主分支中经审查的内容；
5. **stable release space**：Release标记的阶段性版本。

## 建议目录

```text
proposals/       正式提案
research/        研究问题、方法和结果
decisions/       已接受的重要决策
translations/    关联源版本的翻译
schemas/         YAML/JSON数据结构
experiments/     可复现实验说明
```

原始聊天流水、大型数据、音视频和模型权重不应直接提交到Git。

## 权限模型

### L0：只读

- 读取公共仓库；
- 解释、总结和推荐议题；
- 不执行GitHub写入。

### L1：私有草稿

- 整理用户观点；
- 生成Issue、Comment或PR草稿；
- 检查风险；
- 不公开提交。

### L2：确认后写入

- 创建Issue或Comment；
- 在用户Fork创建分支；
- 创建Draft Pull Request；
- 每次公开写入前取得确认。

### L3：维护辅助

- 添加标签；
- 关联记录；
- 运行格式、链接和Schema检查；
- 更新非关键元数据；
- 仍受最小权限和审计约束。

### L4：受保护操作

- 合并主分支；
- 发布Release；
- 修改许可证、治理、权限和安全工作流；
- 删除或隐藏公共历史。

L4默认只能由人类执行，或在可逆、范围清晰的情况下逐次明确授权。不得授予AI长期自主L4权限。

## 连接器与凭证

- OAuth优先于长期令牌；
- 使用PAT时应选择fine-grained token；
- 只授权必要仓库和必要工具集；
- 令牌不得写入仓库、Issue、提示词或日志；
- 公共讨论通常只需要仓库读取和Issues读写；
- PR流程优先写入参与者自己的Fork；
- 默认不允许Secrets、Actions管理、组织管理或仓库删除权限。

## 后续扩展接口

未来其他服务应通过清晰接口接入，而不是替换公共记录：

- GitHub MCP或其他开放工具协议：AI与协作平台连接；
- 对象存储：大型原始数据；
- DVC/lakeFS：数据版本；
- JupyterHub：实验计算；
- OSF：研究项目门户和预注册；
- Zenodo：正式归档和DOI；
- Hugging Face：模型和AI数据集；
- Forgejo、Codeberg和GitLab：镜像、自托管和灾备。

GitHub记录应保存外部对象的标识、版本、校验值、来源和许可，而不是假装所有数据都位于Git仓库中。