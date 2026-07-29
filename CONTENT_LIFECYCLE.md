# Content Lifecycle and Repository Routing / 内容生命周期与仓库路由

Status: `draft-0.2`

本文件规定公开内容如何从自由交流发展为Issue、提案、研究成果、决策或正式规范，以及AI应把不同内容路由到哪里。

交流对象的详细分工见 [`COMMUNICATION_PROTOCOL.md`](COMMUNICATION_PROTOCOL.md)；问题排序、目标立项、审查和发布条件见 [`TEAM_GOVERNANCE.md`](TEAM_GOVERNANCE.md)。

> Discussion是开放交流和问题发现空间；Issue是可追踪的结构化对象；仓库文件是经过整理、审查并具有长期价值的知识。

## 1. Three independent decisions / 三个独立判断

在决定GitHub操作前，AI和参与者应依次回答：

1. **Can it be public? / 能否公开？** 按 `DATA_CLASSIFICATION.md` 分类；只有 `D0` 可以进入本仓库。
2. **What interaction object is needed? / 需要哪种交流对象？** 自由交流使用Discussion；可追踪问题使用Issue；聚焦补充使用Comment；正式修改使用PR。
3. **Where does long-lived knowledge belong? / 长期知识应放在哪里？** 按本文件判断内容类型和生命周期。

不得用目录名称替代数据分类，也不得仅因为文本较长就自动升级为长期文件。

## 2. Lifecycle / 内容生命周期

```text
private draft (D1)
        │ explicit human authorization
        ▼
open conversation
Discussion
        │ trackable question, task or dispute
        ▼
structured public work
Issue · Comment · Draft PR
        │ discussion, translation, evidence and critique
        ▼
formal work
proposal · research · schema · example
        │ Pull Request, review and governance gate
        ▼
accepted knowledge
Decision · Specification · validated result
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
accepted → disputed → revised / superseded / withdrawn
```

## 3. Routing table / 路由表

| Content | First destination | Long-term destination when mature |
|---|---|---|
| Open question, informal idea, onboarding or search for collaborators | Discussion | Issue only when a trackable object emerges |
| New structured question or hypothesis | Issue | `proposals/` or `research/questions/` only when sustained work is justified |
| Focused response, evidence, translation or counterexample | Issue comment | `research/evidence/`, `research/results/` or a linked document when reusable |
| Formal objection to a current result or decision | Linked Issue or comment | revised Decision, Result or Specification when resolved |
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

GitHub Discussions未启用时，可以使用带`type:discussion`标签的Issue作为临时替代，但必须明确其非任务性质。

## 4. From Discussion to Issue / 从Discussion升级为Issue

当开放交流出现以下情况之一时，应创建或关联Issue：

- 已形成明确、可追踪的问题；
- 需要责任人、依赖、里程碑或验证标准；
- 出现需要正式回应的重要争议；
- 需要建立研究问题、工作目标或规范修改；
- 需要形成Proposal、Research或代码变更。

升级记录应包含：

- 来源Discussion；
- 明确问题；
- 已知背景和主要观点；
- 尚缺证据；
- 未解决分歧；
- 建议下一步。

AI不得在无人审阅时自动关闭Discussion或宣布形成共识。

## 5. Repository structure / 仓库目录结构

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

## 6. No user submission folders / 不按用户建立投稿目录

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
- Discussions and Issues already provide authorship, timestamps, labels, links and discussion history.

Contribution attribution should be preserved through GitHub authorship, Discussion and Issue history, commits and explicit metadata.

## 7. Promotion rules / 内容升级规则

### From Issue to proposal

Promote an Issue to `proposals/` only when it includes most of:

- a clearly defined problem;
- a concrete proposed approach;
- alternatives considered;
- risks and trade-offs;
- implementation or validation criteria;
- unresolved questions;
- links to the originating Discussion, Issue and evidence;
- an identified owner or working group;
- required review dimensions.

A long or popular Issue is not automatically a mature proposal.

### From proposal to initiated goal

A proposal may become an organized project goal only after the initiation process in [`TEAM_GOVERNANCE.md`](TEAM_GOVERNANCE.md) records:

- scope and out-of-scope work;
- deliverables;
- success and stop conditions;
- owner or temporary working group;
- dependencies and reviewers;
- human confirmation appropriate to the decision level.

Goal initiation does not pre-approve the final conclusion.

### From proposal to specification

A proposal does not become a specification automatically. Moving content into `specs/` requires:

- explicit acceptance under `GOVERNANCE.md`;
- a focused Pull Request;
- normative language clearly separated from explanation;
- compatibility and migration impact where relevant;
- version, status and source-language metadata;
- at least one human reviewer not acting only as the drafting AI operator;
- additional review and public-review period required by impact level;
- unresolved objections recorded rather than silently removed.

### From research to accepted result

A research result should state:

- question and hypothesis;
- method and data sources;
- data and software licenses;
- software, model and environment versions;
- results and uncertainty;
- limitations and counterexamples;
- reproduction or verification status;
- human and AI roles;
- success criteria established before evaluation where practical;
- material objections and how they were handled.

`accepted` means the project currently recognizes the record; it does not mean universal or permanent truth.

## 8. Issue closure / 议题关闭

Closing an Issue should record:

- why it is being closed;
- the current outcome or conclusion;
- key evidence;
- unresolved objections;
- links to follow-up Proposal, PR, Decision, Specification or Research;
- whether it is completed, rejected, duplicate, deferred or out of scope.

Disagreement should not be erased merely to produce a clean closed state.

## 9. Archive rules / 归档规则

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

## 10. Recommended record metadata / 建议文件元数据

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
  discussion: null
  issue: 42
  submitted_by: github-login
  submitted_at: YYYY-MM-DD

project_governance:
  owner: working-group-or-person
  required_reviews:
    - content-review
    - governance-review
  decision_record: null

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

## 11. Naming guidance / 命名建议

Use stable English paths and identifiers:

```text
proposals/IRIS-RFC-0001/
decisions/IRIS-ADR-0001.md
research/pilots/ai-assisted-participation/
specs/ai-secretary-protocol/spec.md
schemas/research-record.schema.json
```

Names should describe the topic, not the submitting user.

## 12. AI routing algorithm / AI路由算法

When a participant asks AI to contribute, the AI should:

1. classify the source content as `D0`–`D3`, assuming `D1` by default;
2. stop public writing for `D2` or `D3` content;
3. search existing Discussions, Issues, proposals, research and specifications for duplicates or related work;
4. choose the smallest suitable public object;
5. route open-ended conversation or onboarding to Discussion when available;
6. route trackable ideas, questions and disputes to Issues;
7. route focused additions to Issue comments;
8. route mature, reusable work to the appropriate directory through a branch and Pull Request;
9. never write directly into `specs/` without an accepted proposal or recorded governance basis;
10. identify required governance and review roles for formal work;
11. show the user the final public content or diff and obtain explicit confirmation;
12. disclose material AI assistance and return links to the actual GitHub result.

AI may recommend status, priority, reviewers and next steps, but cannot independently decide goal initiation, final priority, acceptance or release.

## 13. Source of truth order / 当前信息查找顺序

When answering questions about the project, AI should search in this order:

1. current `specs/` and `decisions/`;
2. current governance files;
3. active proposals and research records;
4. Issues, Pull Requests and formal reviews;
5. Discussions and informal summaries;
6. `archive/`;
7. Git history, tags and Releases.

If sources conflict, AI must state which document is current and why.
