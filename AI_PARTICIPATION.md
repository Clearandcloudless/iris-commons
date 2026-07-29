# 通过AI参与 Iris Commons

> 本文件既写给人类，也写给代表人类工作的AI助手。

Iris Commons 的目标是让参与者**不必先学习GitHub和项目文档**。完成一次连接或授权后，你可以继续使用自然语言，让AI帮助你阅读项目、寻找议题、整理观点、提交Issue、参与讨论或准备Pull Request。

仓库地址：

```text
https://github.com/Clearandcloudless/iris-commons
```

## 最快开始：不安装任何工具

把下面的提示词发送给能够访问网页的GPT、Gemini、Claude或其他AI：

```text
请阅读 https://github.com/Clearandcloudless/iris-commons ，优先读取 AI_PARTICIPATION.md、AGENTS.md、LANGUAGE_POLICY.md、GOVERNANCE.md 和当前开放Issues。

使用我正在使用的语言向我说明：
1. 这个项目试图解决什么问题；
2. 当前有哪些适合我参与的讨论；
3. 根据我的背景，哪一种贡献最有价值。

不要要求我自己阅读GitHub文档。你负责检索、解释和整理。
在创建公开Issue、评论、分支或Pull Request之前，先向我展示最终内容并取得明确确认。
```

这种方式不要求AI拥有GitHub写权限。AI可以先生成可直接提交的Issue、评论或PR内容，再由你在GitHub网页中发布。

## 推荐工作方式

Iris Commons支持三个参与等级。

### 方式A：AI阅读，用户提交

适合第一次参与或不愿授予GitHub权限的用户。

```text
AI读取公开仓库
  → 找到相关Issue
  → 与用户讨论
  → 生成最终提交文本
  → 用户在GitHub网页确认并发布
```

优点：零配置、权限最小。  
限制：最后一步仍需用户打开GitHub。

### 方式B：AI连接GitHub，确认后代为提交

适合希望长期参与但不想学习GitHub操作的用户。

```text
一次授权GitHub
  → AI读取仓库和Issues
  → 用户使用自然语言表达
  → AI生成公开草稿
  → 用户确认
  → AI创建Issue、评论或草稿PR
```

推荐使用OAuth或细粒度令牌，只授予完成任务所需的最低权限。

### 方式C：AI代理处理完整贡献流程

适合需要修改文档、协议、数据结构或代码的贡献者。

```text
Fork或克隆仓库
  → AI创建分支
  → 修改文件并检查差异
  → 用户审阅
  → AI提交并创建Pull Request
```

AI不得自动合并主分支，也不得在未确认时公开私人对话或本地文件。

# 主流AI接入方式

产品界面和套餐可能变化。以下以开放、可迁移的流程为准；无法使用某项集成时，始终可以退回“AI阅读、用户提交”方式。

## ChatGPT

### ChatGPT GitHub应用：适合阅读、理解和寻找议题

1. 打开ChatGPT的 **Settings / 设置 → Apps / 应用**；
2. 找到GitHub并完成授权；
3. 只选择确实需要访问的仓库；
4. 在对话中粘贴本文件顶部的“最快开始”提示词。

ChatGPT内置GitHub应用主要适合读取、搜索、分析和引用仓库内容。具体界面是否提供写入工具取决于当前产品体验和权限；没有写入能力时，让ChatGPT生成最终文本，再由你提交。

官方说明：<https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt>

### Codex：适合修改仓库并创建Pull Request

1. 在Codex中连接GitHub；
2. 选择或创建与 `iris-commons` 相关的环境；
3. 让Codex先读取 `AGENTS.md` 和本文件；
4. 使用“Ask”模式理解议题，使用可修改仓库的模式准备变更；
5. 审阅diff和PR内容后再公开提交。

推荐任务提示词：

```text
阅读AGENTS.md、AI_PARTICIPATION.md和LANGUAGE_POLICY.md。
根据Issue #编号提出一个最小、可审查的修改方案。
使用分支和Pull Request，不要直接修改受保护主分支。
保留原作者语言，并披露AI参与方式。
在提交或创建PR前向我展示diff摘要和公开文本。
```

官方说明：<https://help.openai.com/en/articles/11369540-getting-started-with-codex>

## Gemini

### 普通Gemini对话

将仓库URL和“最快开始”提示词交给Gemini。若当前界面只能读取网页，让Gemini生成可提交草稿即可。

### Gemini CLI + GitHub MCP：适合长期读写

Gemini CLI支持通过MCP连接外部工具。GitHub官方MCP服务器可以向兼容客户端提供仓库、Issue和Pull Request工具。

安全建议：

- 优先使用OAuth；
- 使用令牌时选择fine-grained PAT；
- 仅读取公开内容时不要授予写权限；
- 参与讨论通常只需要Metadata和Contents读取、Issues读写；
- 创建PR时才增加Pull Requests及必要的Contents权限；
- 不要把令牌写进仓库或提示词。

Gemini CLI官方GitHub MCP示例使用Docker启动GitHub MCP服务器，并通过环境变量传入令牌。完成配置后运行：

```text
gemini
```

然后发送：

```text
读取本仓库的GEMINI.md和AI_PARTICIPATION.md。
检查当前开放Issues，用我的语言推荐一个适合参与的议题。
只在我确认后使用GitHub工具公开提交内容。
```

官方说明：

- <https://geminicli.com/docs/cli/tutorials/mcp-setup/>
- <https://geminicli.com/docs/tools/mcp-server/>

## Claude

### Claude网页或桌面对话

直接提供仓库URL和“最快开始”提示词。没有GitHub写入权限时，让Claude准备提交内容。

### Claude Code：适合Fork、文档修改和Pull Request

安装并登录Claude Code后，可以使用GitHub CLI完成Fork和PR流程：

```bash
gh auth login
gh repo fork Clearandcloudless/iris-commons --clone
cd iris-commons
claude
```

进入Claude Code后发送：

```text
先读取CLAUDE.md、AGENTS.md和AI_PARTICIPATION.md。
帮助我选择一个Issue并完成贡献。
任何公开提交前先展示最终文本或diff；不要自动合并。
```

Claude Code也支持MCP，可在需要时连接GitHub MCP服务器。

官方说明：

- <https://docs.anthropic.com/en/docs/claude-code/getting-started>
- <https://docs.anthropic.com/en/docs/mcp>

## GitHub Copilot / VS Code

GitHub提供并维护远程GitHub MCP服务器。在VS Code中可以从MCP Registry安装：

1. 打开Extensions；
2. 搜索 `@mcp github`；
3. 安装GitHub MCP Server；
4. 通过OAuth登录；
5. 在Copilot Chat中选择Agent模式；
6. 让代理读取 `.github/copilot-instructions.md` 和本文件。

推荐提示词：

```text
按照仓库的copilot instructions和AI_PARTICIPATION.md工作。
先总结当前Issues并询问我的兴趣；不要默认修改文件。
需要公开写入时，先展示内容并请求确认。
```

官方说明：<https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/set-up-the-github-mcp-server>

## 其他MCP兼容AI或本地模型

GitHub远程MCP服务器地址为：

```text
https://api.githubcopilot.com/mcp/
```

支持HTTP MCP和OAuth的客户端通常可以连接该地址。也可以自行运行GitHub MCP Server的本地容器。

连接后建议只启用必要工具集：

```text
repos
issues
pull_requests
```

不要默认启用全部工具，不要授予Actions、Secrets、组织管理或仓库删除权限。

GitHub官方说明：

- <https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/set-up-the-github-mcp-server>
- <https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/configure-toolsets>

# 你可以直接对AI说什么

## 找一个适合参与的议题

```text
读取Iris Commons当前开放Issues，根据我的背景和语言推荐三个参与方向。
分别说明所需投入、已有争议和我可以提供的独特价值。
```

## 提出一个新想法

```text
我有下面这个想法：[直接用自己的语言描述]。
请根据Iris Commons的Issue模板帮我整理，但保留我的原始表达。
区分事实、推断、疑问和建议，补充需要验证的部分。
最后生成公开草稿，在我确认前不要提交。
```

## 参与现有讨论

```text
读取Issue #编号及全部评论。
用我的语言解释各方真正的分歧，不要只给多数意见。
帮助我形成一条有新信息、有证据或有明确反例的评论。
```

## 让另一个模型审查

```text
把当前提案交给一个独立批判角色审查。
重点寻找错误假设、语言歧义、利益冲突、不可证伪部分和现实失败条件。
不要因为多个模型意见一致就提高结论可信度。
```

## 翻译贡献

```text
保留原文，生成目标语言译文。
标出无法一一对应的术语、文化背景和可能改变含义的地方。
不要把译文写成比原文更确定的结论。
```

## 修改文档或协议

```text
针对Issue #编号创建一个范围最小的修改。
遵守LANGUAGE_POLICY.md：机器字段和路径使用英文，参与者原始观点保留原语言。
生成分支、commit和PR草稿，但在公开提交前让我审阅diff。
```

# AI助手必须执行的工作流程

当AI收到“帮助我参与Iris Commons”之类的请求时，应：

1. 读取 `AGENTS.md`；
2. 读取本文件、`LANGUAGE_POLICY.md`、`GOVERNANCE.md` 和相关Issue；
3. 使用用户当前语言交流，不强迫用户改用英文；
4. 主动解释GitHub对象，不要求用户自己寻找文档；
5. 将原文、译文、摘要、推断和建议分开；
6. 对外部事实进行检索并提供来源，或明确标注尚未核查；
7. 公开前检查个人信息、密钥、版权和现实安全风险；
8. 在任何公开写操作前展示最终内容并取得明确确认；
9. 使用用户自己的GitHub身份提交，不冒充独立人类贡献者；
10. 在公开内容中披露AI承担的角色和人工审阅状态；
11. 写入失败时给出可复制的完整草稿，而不是让用户重新整理；
12. 不自动合并主分支、发布Release或修改治理规则。

# 语言规则摘要

- 用户和社区讨论：任何语言；
- 参与者观点：原始语言是权威表达；
- 翻译和摘要：派生视图，必须可追溯；
- 仓库路径、字段名、状态值、标签和接口：英文；
- 技术规范：逐步建立英文规范版和多语言翻译版；
- AI与用户交流：优先使用用户语言；
- 公共桥接摘要：必要时提供英文，但不能成为参与门槛。

完整规则见 [`LANGUAGE_POLICY.md`](LANGUAGE_POLICY.md)。

# 权限底线

首次连接AI时，建议按以下顺序逐步授权：

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