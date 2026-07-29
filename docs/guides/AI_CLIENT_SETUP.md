# AI Client Setup Guide / 主流AI客户端接入指南

This guide contains detailed setup notes. New participants should begin with [`START_HERE.md`](../../START_HERE.md), not this file.

本文件保存详细客户端配置。首次参与请先阅读[`START_HERE.md`](../../START_HERE.md)。

## Common operating rule

Whichever client you use:

1. give it the repository URL;
2. tell it to read `START_HERE.md` and `AGENTS.md` first;
3. grant the minimum GitHub permissions needed;
4. require it to show every final public text or diff before writing;
5. do not grant unattended merge, Release, Secrets or administration permissions.

## No-write mode

Any AI that can read webpages can participate without GitHub write access. Ask it to inspect the repository and prepare a complete copy-ready Issue, comment or Pull Request draft.

Suggested prompt:

```text
Read https://github.com/Clearandcloudless/iris-commons.
Start with START_HERE.md and AGENTS.md.
Use my language and inspect current Issues.
Recommend one concrete contribution and prepare the complete public draft.
Do not write to GitHub. Do not summarize every protocol.
```

## ChatGPT

### GitHub app: reading and project understanding

1. Open **Settings → Apps** in ChatGPT.
2. Connect GitHub.
3. Grant access only to the repository you need.
4. use the prompt above.

When write tools are unavailable, request a complete final draft and submit it through GitHub yourself.

Official guide: <https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt>

### Codex: repository changes and Pull Requests

1. Connect GitHub in Codex.
2. Select the repository or a fork.
3. Ask Codex to read `START_HERE.md` and `AGENTS.md`.
4. Use an Issue as the basis for a focused change.
5. Review the diff and PR text before public submission.

Suggested prompt:

```text
Read START_HERE.md and AGENTS.md.
Work on Issue #NUMBER using the smallest relevant rule set.
Do not read every Markdown file.
State the D0 classification, target path and required human review.
Show me the final diff and PR text before creating the Pull Request.
```

Official guide: <https://help.openai.com/en/articles/11369540-getting-started-with-codex>

## Gemini

### Gemini web or app

Provide the repository URL and the no-write prompt. Ask Gemini to prepare the final contribution when GitHub write tools are unavailable.

### Gemini CLI with GitHub MCP

Gemini CLI can connect to GitHub tools through MCP. Prefer OAuth or a fine-grained token scoped to one repository.

Suggested prompt after connection:

```text
Read START_HERE.md, GEMINI.md and AGENTS.md.
Inspect current Issues and recommend one contribution in my language.
Load additional project rules only when the task needs them.
Before any public GitHub write, show the final content, classification and destination.
```

Official guides:

- <https://geminicli.com/docs/cli/tutorials/mcp-setup/>
- <https://geminicli.com/docs/tools/mcp-server/>

## Claude

### Claude web or desktop

Provide the repository URL and ask Claude to create a complete copy-ready draft.

### Claude Code

```bash
gh auth login
gh repo fork Clearandcloudless/iris-commons --clone
cd iris-commons
claude
```

Then use:

```text
Read START_HERE.md, CLAUDE.md and AGENTS.md.
Help me select one current Issue and make the smallest reviewable change.
Load specialist rules only when relevant.
Show the public text and diff before committing or opening a PR.
```

Official guides:

- <https://docs.anthropic.com/en/docs/claude-code/getting-started>
- <https://docs.anthropic.com/en/docs/mcp>

## GitHub Copilot and VS Code

1. Connect the GitHub MCP Server or use the available GitHub tools.
2. Authenticate through OAuth.
3. Open the repository.
4. Use Agent mode when repository changes are needed.
5. The agent should read `.github/copilot-instructions.md`, `START_HERE.md` and `AGENTS.md`.

Suggested prompt:

```text
Follow the repository Copilot instructions.
Inspect current Issues and propose one focused next step.
Do not default to editing files or reading all protocols.
Before a public write, show the exact content, classification, route and diff.
```

Official guide: <https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/set-up-the-github-mcp-server>

## Other MCP-compatible or local-model clients

GitHub's remote MCP endpoint is commonly available at:

```text
https://api.githubcopilot.com/mcp/
```

Enable only necessary tool groups, such as repository reading, Issues and Pull Requests. Do not enable Secrets, organization administration, repository deletion or unrestricted private-repository access by default.

## Permission progression

```text
public read only
→ Issues or Discussions write
→ Pull Requests and Reviews
→ content writes to the user's fork or an authorized branch
```

Avoid by default:

- repository administration;
- Secrets access;
- arbitrary workflow modification;
- organization membership management;
- access to unrelated private repositories;
- unattended protected-branch merge;
- unattended Release publication.

## Expected AI behavior

After setup, the user should be able to speak naturally. The AI should:

- use the user's language;
- inspect current work;
- recommend a focused next step;
- preserve the user's original meaning;
- classify and route the proposed public content;
- prepare a complete contribution;
- request confirmation for each public write;
- return the resulting URL.

Configuration is successful only when the user does not need to study GitHub mechanics or receive a long protocol lecture before contributing.
