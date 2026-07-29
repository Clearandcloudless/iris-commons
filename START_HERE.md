# Start Here / 从这里开始

> Iris Commons helps people join public GitHub collaboration through the AI assistant they already use.
>
> Iris Commons让普通人通过自己熟悉的AI参与GitHub公共协作。

## What is this? / 这是什么？

You can speak in your own language. Your AI can help you find an existing discussion, preserve your original meaning, prepare a contribution and handle GitHub mechanics. Humans still authorize every public contribution and make final decisions.

你可以直接使用自己的语言表达。AI负责寻找相关讨论、保留原意、整理贡献内容和处理GitHub操作；公开发布和最终决定仍由人类负责。

You do **not** need to read the whole repository before participating.

你**不需要**先读完整个仓库。

## What can I do now? / 我现在能做什么？

Choose one action:

1. **Ask your AI to guide you. / 让AI带你参与**

   Send this prompt to ChatGPT, Gemini, Claude, Copilot or another AI that can access GitHub:

   ```text
   Read https://github.com/Clearandcloudless/iris-commons.
   Start with START_HERE.md and AGENTS.md only.
   Use my language. Inspect current open Issues and recommend one concrete next step.
   Do not summarize every protocol or ask me to read multiple files.
   Before any public GitHub write, show me the final text, classification and destination, then obtain my explicit confirmation.
   ```

2. **Browse current work. / 查看当前议题**

   Open the [current Issues](https://github.com/Clearandcloudless/iris-commons/issues) and contribute an idea, critique, source, review or pilot proposal.

## What should an AI read? / AI应该读取什么？

Default minimum:

```text
START_HERE.md
→ AGENTS.md
→ the relevant Issue or Pull Request
```

Load additional rules only when the task needs them:

- public or sensitive content → `DATA_CLASSIFICATION.md`
- choosing Discussion, Issue or PR → `COMMUNICATION_PROTOCOL.md`
- creating long-lived files → `CONTENT_LIFECYCLE.md`
- language or translation → `LANGUAGE_POLICY.md`
- governance or approval → `GOVERNANCE.md`
- security-sensitive work → `SECURITY.md` and `docs/threat-model.md`

Do not read and summarize every Markdown file by default.

## Non-negotiable boundary / 不可妥协的边界

Private conversations, uploads and drafts are not public merely because an AI can access them. Every public write requires a reviewed public version and explicit human authorization.

AI能访问私人对话、文件或草稿，不代表这些内容已获准公开。每次公开写入前，都必须展示最终公开版本并获得人类明确确认。

More details:

- [AI participation guide / AI参与指南](AI_PARTICIPATION.md)
- [Contribution guide / 贡献指南](CONTRIBUTING.md)
- [Current governance / 当前治理](GOVERNANCE.md)
