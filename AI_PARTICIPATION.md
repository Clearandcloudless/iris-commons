# Participate through AI / 通过AI参与

> Start with [`START_HERE.md`](START_HERE.md). This file explains the participation workflow; detailed client configuration is in [`docs/guides/AI_CLIENT_SETUP.md`](docs/guides/AI_CLIENT_SETUP.md).
>
> 请先阅读[`START_HERE.md`](START_HERE.md)。本文件只说明参与流程；ChatGPT、Codex、Gemini、Claude、Copilot和MCP的详细配置见[`docs/guides/AI_CLIENT_SETUP.md`](docs/guides/AI_CLIENT_SETUP.md)。

Iris Commons is designed so participants do not need to learn GitHub or read every protocol before contributing.

## Give this to your AI / 把这段话交给AI

```text
Read https://github.com/Clearandcloudless/iris-commons.
Start with START_HERE.md and AGENTS.md only, then inspect the current open Issues.
Use my language and recommend one concrete next step based on my background.
Do not summarize every protocol or ask me to read multiple files.
Load specialist rules only when the task requires them.
Before any public GitHub write, show me the final content or diff, D0–D3 classification, destination and required human review, then obtain my explicit confirmation.
```

## Three participation modes / 三种参与方式

### A. AI reads, user submits / AI读取，用户提交

```text
AI reads public repository
→ recommends relevant Issue
→ prepares complete public draft
→ user reviews and submits through GitHub
```

No GitHub write permission is needed.

### B. Connected AI submits after confirmation / AI连接GitHub并在确认后提交

```text
AI reads repository and Issues
→ user speaks naturally
→ AI classifies, routes and drafts
→ user confirms this exact public write
→ AI creates Issue, comment or Draft PR
```

Use OAuth or a fine-grained token with the smallest repository and operation scope.

### C. Repository agent prepares a Pull Request / 仓库代理准备PR

```text
fork or clone
→ read START_HERE.md and AGENTS.md
→ work from an Issue
→ edit the correct path
→ show diff and risks
→ user confirms
→ open Pull Request
→ human review
```

AI must not independently merge protected branches, publish Releases, change governance or expose private material.

## The three decisions before a public write / 公开前的三个判断

### 1. Can it be public? / 能否公开？

- `D0 public-ready`: may be published;
- `D1 review-required`: keep private until reviewed;
- `D2 restricted`: use a separate controlled space;
- `D3 prohibited`: do not store or publish.

User conversations, uploads and generated drafts are `D1` by default. A public Issue, comment, branch or Draft PR is already public.

### 2. What is the smallest suitable GitHub object? / 最小合适对象是什么？

```text
open-ended conversation → Discussion when available
trackable idea or task  → Issue
focused evidence/reply  → Issue comment
long-lived change       → branch + Pull Request
formal independent check→ Review
```

Ordinary ideas do not become repository files automatically.

### 3. Does it need a long-lived directory and human approval? / 是否进入长期目录？

```text
mature proposal        → proposals/
structured research    → research/
accepted rationale     → decisions/
current normative rule → specs/
machine-readable model → schemas/
worked example         → examples/
maintained translation → translations/
historical material    → archive/
```

Never write directly into `specs/` without an accepted proposal or recorded governance basis.

## Current MVP governance / 当前最小治理

The active project governance is deliberately small:

- the Maintainer executes repository operations and records reasons;
- human Reviewers are invited for each relevant Issue or PR;
- disputes are recorded in the relevant Issue;
- a conflicted Maintainer or major rule change requires external human review;
- future role structures in `TEAM_GOVERNANCE.md` are optional and not currently staffed.

AI may assist but cannot appoint people, set final priority, approve formal work, merge protected branches or publish Releases.

## Useful requests / 可直接提出的请求

### Find one contribution

```text
Inspect the current Issues. Based on my language and background, recommend up to three concrete paths and choose one immediately executable next step. Do not give me a repository-wide protocol summary.
```

### Submit an idea

```text
Treat my idea as a private D1 draft first. Search for related work, preserve my original wording and prepare the smallest suitable Issue or comment. Show the D0 public version before submission. Do not create a repository file.
```

### Change a document or protocol

```text
Work from Issue #NUMBER. Load only the specialist rules needed for this change. Identify the target path and required human review, then show the complete diff and PR text before using GitHub write tools.
```

### Review an existing proposal

```text
Read PR #NUMBER and its linked Issue. State which dimensions I am reviewing, list blocking problems, non-blocking suggestions and unreviewed areas. Preserve important objections and let me confirm the final Review.
```

## Public-write checklist / 公开写入检查

Before writing, the AI must show:

- the exact public text or diff;
- the selected `D0` classification;
- the chosen GitHub object or directory;
- material privacy, copyright, factual and safety risks;
- the needed human review;
- the AI's material role.

A previous connection or approval is not unlimited continuing authorization.

## Detailed setup

See [`docs/guides/AI_CLIENT_SETUP.md`](docs/guides/AI_CLIENT_SETUP.md) for ChatGPT, Codex, Gemini, Claude, Copilot, MCP and local-model setup.

Iris Commons removes participation barriers—not safety boundaries, governance or human responsibility.
