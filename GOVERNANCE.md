# Governance / 当前治理规则

Status: `draft-0.2`  
Current mode: **MVP Governance**

This file is the current operational governance for Iris Commons. The broader role catalogue in [`TEAM_GOVERNANCE.md`](TEAM_GOVERNANCE.md) is an optional expansion model and is **not currently active**.

本文件是Iris Commons当前生效的最小治理规则。`TEAM_GOVERNANCE.md`中的完整角色体系属于未来可选扩展，不代表这些职位已经设立，也不得阻塞当前试验和普通贡献。

## 1. Current active roles / 当前生效角色

### Maintainer / 维护者

The repository owner currently acts as Maintainer and is responsible for:

- repository settings, labels, templates and branch protection;
- executing merges after required review;
- recording reasons for material repository actions;
- responding to privacy, security and abuse incidents;
- keeping current rules distinguishable from proposals and archived material.

The Maintainer is not the final judge of research truth and may not be the sole approver of their own major governance, specification or research work.

### Temporary human Reviewer / 临时人类审查者

Reviewers are invited per Issue or Pull Request. There are no permanent review seats in the MVP stage.

A Reviewer should state the dimensions actually reviewed, for example:

```text
content · sources · method · language · security · ethics · governance · implementation
```

The Reviewer is responsible only for the dimensions they explicitly reviewed.

### Simple appeal path / 简易申诉路径

A participant who disputes classification, closure, routing, translation, priority or review should first explain the objection in the relevant Issue.

If the dispute cannot be resolved:

- the Maintainer records a provisional, reviewable decision and reasons;
- when the Maintainer has a conflict of interest, at least one external human participant must review the decision;
- major rule changes also require at least one external human review during the MVP stage;
- the decision may be reopened when new evidence or participants become available.

No permanent Appeal Panel is active.

## 2. What is not currently active / 当前未启用的角色

The following functions are described in `TEAM_GOVERNANCE.md` but are not currently staffed:

- Triage Steward;
- Roadmap Steward or Council;
- permanent Working Group Lead positions;
- Reviewer Pool or formal Review Board;
- Release Steward as a separate office;
- Ombudsperson or Appeal Panel.

The Maintainer may perform routine triage and release administration, and participants may form temporary working groups. Naming a future function does not create an office or an approval gate.

## 3. Activation conditions for expanded governance / 扩展治理启用条件

An additional role or committee should be activated only when a real operating need is recorded in an Issue. Relevant signals include:

- at least four consistently active human contributors over multiple weeks;
- two or more concurrent workstreams that cannot be coordinated informally;
- recurring releases that require a separate release check;
- repeated triage or prioritization disputes;
- repeated conflicts of interest or appeals;
- high-impact research, privacy, security or ethical risk requiring specialist review;
- a workload that causes the current Maintainer to become a bottleneck.

The activation Issue must define:

- the problem the role solves;
- its powers and limits;
- who appoints or removes the role;
- duration or review date;
- conflicts of interest;
- appeal and audit path;
- conditions for dissolving the role.

Expanded governance is not a maturity badge. Roles should be removed or combined when the need disappears.

## 4. Decision levels / 决策层级

### Routine maintenance

Typos, broken links, formatting, non-semantic translation corrections and non-critical metadata may be merged by the Maintainer.

Routine edits must not change authorship, meaning, status, conclusions or normative rules.

### Ordinary substantive work

A document, research record, protocol or implementation change should:

1. have a relevant Issue or clearly recorded basis;
2. be submitted through a focused Pull Request;
3. identify data classification, source language, AI assistance and target area;
4. receive at least one human review when it changes material meaning;
5. be merged by the Maintainer after blocking concerns are resolved or explicitly recorded.

### Major governance, license or irreversible changes

Changes to licenses, Maintainer powers, privacy boundaries, AI public-write authority, normative language or irreversible public history require:

- a clearly marked governance proposal;
- alternatives, impact and risks;
- a public review period appropriate to the impact;
- at least one external human reviewer while the project has only one Maintainer;
- a recorded decision and follow-up review plan.

The project does not require two Maintainers before it has two qualified Maintainers. It requires external review so that the sole Maintainer does not self-approve major changes.

## 5. Decision method / 决策方法

The default method is:

> **rough consensus + recorded objections + reviewable decision**

A decision may be accepted, narrowed, piloted, marked disputed, returned for evidence, deferred, rejected, withdrawn or superseded.

Votes, reactions, comment counts, English fluency or agreement between AI models do not by themselves establish priority or truth.

## 6. Participation rights / 参与权

Participants may:

- use any language;
- use an AI assistant of their choice;
- preserve original wording and minority opinions;
- question project, Maintainer and AI decisions;
- request review of classification, translation, routing or closure;
- contribute through evidence, critique, translation, synthesis, reproduction or review without writing code.

No contribution should be deprioritized solely because the participant does not know GitHub, does not use English or does not use an expensive model.

Claims remain subject to evidence, logic, ethics and safety review.

## 7. AI authority boundary / AI权限边界

AI may:

- explain the project and recommend current Issues;
- prepare private drafts;
- classify and route content as a recommendation;
- search for related work;
- prepare summaries, translations, reviews and diffs;
- execute a scoped public write after the human confirms that exact content.

AI may not independently:

- authorize private material for publication;
- close significant Issues or reject proposals;
- set final priority;
- appoint people or create governance offices;
- approve its own draft;
- merge protected branches;
- declare research, decisions or specifications accepted;
- publish Releases;
- change licenses, permissions, Secrets or governance.

A previous connection or general permission is not unlimited continuing authorization.

## 8. Public-write confirmation / 公开写入确认

Before every public Discussion, Issue, comment, branch, commit, Pull Request or Review, the AI should show:

- the exact public content or a clear diff;
- the `D0` classification and checks performed;
- the target GitHub object or directory;
- material privacy, copyright, factual and safety risks;
- the required human review;
- the AI's role.

The participant must explicitly confirm the proposed public write.

## 9. Multilingual authority / 多语言权威

Participant-authored original-language content remains authoritative for that participant's meaning. Translations and summaries are derivatives and must not silently increase certainty, remove objections or replace the source text.

Machine-facing identifiers use English. English is an interoperability bridge, not a participation requirement.

See [`LANGUAGE_POLICY.md`](LANGUAGE_POLICY.md).

## 10. Urgent action / 紧急措施

The Maintainer may temporarily hide, close or restrict content that exposes credentials, personal data, malicious payloads, harassment, threats, clear rights violations or uncontrolled automated writes.

Urgent action should minimize further exposure, record a safe explanation and preserve an appeal path where possible.

## 11. Independent template projects / 独立模板项目

Teams that copy Iris Commons are independent. They may adopt, simplify or replace this governance, but should clearly publish:

1. who maintains the repository;
2. what requires human review;
3. who may merge and release;
4. how conflicts and appeals are handled;
5. what AI may and may not do.

The first Iris Commons pilot must be able to run using only this MVP governance.
