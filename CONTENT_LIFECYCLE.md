# Content Lifecycle and Repository Routing / 内容生命周期与仓库路由

Status: `draft-0.1`

本文件规定公开内容如何从想法发展为提案、研究成果、决策或正式规范，以及AI应把不同内容路由到哪里。

> Issue 是投稿箱和讨论现场；仓库文件是经过整理、审查并具有长期价值的知识。

## 1. Two independent decisions / 两个独立判断

在决定GitHub操作前，AI和参与者应依次回答：

1. **Can it be public? / 能否公开？** 按 `DATA_CLASSIFICATION.md` 分类；只有 `D0` 可以进入本仓库。
2. **Where does it belong? / 应放在哪里？** 按本文件判断内容类型和生命周期。

不得用目录名称替代数据分类。

## 2. Lifecycle / 内容生命周期

```text
private draft (D1)
        │ explicit human authorization
        ▼
public discussion
Issue · Comment · Draft PR
        │ discussion, translation, evidence and critique
        ▼
structured work
proposal · research · schema · example
        │ Pull Request and review
        ▼
accepted knowledge
decision · specification · validated result
        │ stable version when appropriate
        ▼
Release / tag
        │ withdrawn, superseded or completed
        ▼
archive, while Git preserves ordinary version history
```

Suggested states:

```text
idea → discussing → proposed → under-review → accepted
                                      ├→ rejected
                                      └→ withdrawn
accepted → implemented / reproduced / validated
accepted → disputed → revised / superseded
```

## 3. Routing table / 路由表

| Content | First destination | Long-term destination when mature |
|---|---|---|
| New idea, question or hypothesis | Issue | `proposals/` or `research/questions/` only when sustained work is justified |
| Focused response, evidence, translation or counterexample | Issue comment | `research/evidence/`, `research/results/` or a linked document when reusable |
| Complete design or governance proposal | Issue, then branch and PR | `proposals/` |
| Research question or evidence review | Issue | `research/questions/` or `research/evidence/` |
| Public-interest pilot | Pilot Issue | `research/pilots/` |
| Reproducible result or final report | Linked Issue and PR | `research/results/` |
| Accepted project decision and rationale | Proposal or Issue + PR | `decisions/` |
| Current normative protocol or implementation specification | Accepted proposal + PR | `specs/` |
| Machine-readable structure | Linked proposal or spec + PR | `schemas/` |
| Non-normative worked example | Issue or PR | `examples/` |
| Maintained translation | Linked source file + PR | `translations/` or README language variant |
| Withdrawn, superseded or completed material still worth reading | Existing record + PR | `archive/` |

## 4. Repository structure / 仓库目录结构

```text
docs/          explanatory guides and concepts
governance/    project governance and community rules
proposals/     formal RFC-style proposals
research/      questions, evidence, pilots and results
specs/         current normative specifications
decisions/     accepted decisions and rationale
schemas/       machine-readable schemas and enums
examples/      non-normative examples
translations/  translations linked to source revisions
archive/       withdrawn, superseded or completed material
```

Existing root documents remain authoritative during the initial migration. They should be moved only through focused Pull Requests that update all links and translation references.

## 5. No user submission folders / 不按用户建立投稿目录

Do not create structures such as:

```text
users/alice/ideas/
users/bob/questions/
submissions/misc/
```

Reasons:

- discussion becomes fragmented by identity rather than topic;
- duplicate ideas are harder to discover and merge;
- personal-data and deletion expectations become unclear;
- large numbers of low-value files reduce repository signal;
- Issues already provide authorship, timestamps, labels, links and discussion history.

Contribution attribution should be preserved through GitHub authorship, Issue history, commits and explicit metadata.

## 6. Promotion rules / 内容升级规则

### From Issue to proposal

Promote an Issue to `proposals/` only when it includes most of:

- a clearly defined problem;
- a concrete proposed approach;
- alternatives considered;
- risks and trade-offs;
- implementation or validation criteria;
- unresolved questions;
- links to the originating Issue and discussion.

### From proposal to specification

A proposal does not become a specification automatically. Moving content into `specs/` requires:

- explicit acceptance under `GOVERNANCE.md`;
- a focused Pull Request;
- normative language clearly separated from explanation;
- compatibility and migration impact where relevant;
- version, status and source-language metadata;
- at least one human reviewer not acting only as the drafting AI operator.

### From research to accepted result

A research result should state:

- question and hypothesis;
- method and data sources;
- data and software licenses;
- software, model and environment versions;
- results and uncertainty;
- limitations and counterexamples;
- reproduction or verification status;
- human and AI roles.

## 7. Archive rules / 归档规则

Git already preserves ordinary version history. Do not copy every old revision into `archive/`.

Use `archive/` only when a document has left the active workflow but remains useful, such as:

- a withdrawn proposal;
- a superseded specification no longer valid as current guidance;
- a completed pilot no longer actively maintained;
- a historical design retained for context.

Current and archived documents must link to each other using fields such as:

```yaml
status: superseded
superseded_by: specs/example/spec.md
archived_at: YYYY-MM-DD
```

AI must never present an archived document as the current rule without clearly stating its status.

## 8. Recommended record metadata / 建议文件元数据

Important long-lived files should use YAML front matter when practical:

```yaml
---
id: IRIS-RFC-0007
type: proposal
title: Multilingual discussion structure
status: discussing
source_language: zh-CN
normative: false

origin:
  issue: 42
  submitted_by: github-login
  submitted_at: YYYY-MM-DD

ai_assistance:
  used: true
  provider: OpenAI
  model: model-name-or-unknown
  roles:
    - drafting
    - translation
  human_reviewed: true

publication:
  classification: D0
  license: CC-BY-4.0

relations:
  supersedes: null
  superseded_by: null
---
```

Public metadata must not expose private conversation identifiers, internal paths or unnecessary personal information.

## 9. Naming guidance / 命名建议

Use stable English paths and identifiers:

```text
proposals/IRIS-RFC-0001/
decisions/IRIS-ADR-0001.md
research/pilots/ai-assisted-participation/
specs/ai-secretary-protocol/spec.md
schemas/research-record.schema.json
```

Names should describe the topic, not the submitting user.

## 10. AI routing algorithm / AI路由算法

When a participant asks AI to contribute, the AI should:

1. classify the source content as `D0`–`D3`, assuming `D1` by default;
2. stop public writing for `D2` or `D3` content;
3. search existing Issues, proposals, research and specifications for duplicates or related work;
4. choose the smallest suitable public object;
5. route ordinary ideas and questions to Issues, not files;
6. route focused additions to Issue comments;
7. route mature, reusable work to the appropriate directory through a branch and Pull Request;
8. never write directly into `specs/` without an accepted proposal or recorded governance basis;
9. show the user the final public content or diff and obtain explicit confirmation;
10. disclose material AI assistance and return links to the actual GitHub result.

## 11. Source of truth order / 当前信息查找顺序

When answering questions about the project, AI should search in this order:

1. current `specs/` and `decisions/`;
2. current governance files;
3. active proposals and research records;
4. Issues and Pull Requests;
5. `archive/`;
6. Git history, tags and Releases.

If sources conflict, AI must state which document is current and why.