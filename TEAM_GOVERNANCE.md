# Expanded Team Governance / 扩展团队治理参考

Status: `draft-0.2`  
Operational status: **optional and not currently active**

The current active rules are in [`GOVERNANCE.md`](GOVERNANCE.md). This file is a menu of governance functions for projects that have outgrown the MVP model. It does not create permanent offices, committees or approval gates.

当前生效规则见[`GOVERNANCE.md`](GOVERNANCE.md)。本文件仅为规模扩大后的可选治理模块，不代表下列角色已经设立，也不得阻塞普通Issue、PR或首个公益试验。

## Design principle / 设计原则

> Define a function only when a real workload or risk requires it; create a role only when someone can actually perform it.
>
> 先证明存在真实职责，再设置角色；先确认有人承担，再建立组织。

Roles may be combined, rotated or temporary. The author of major work must not be its only approver. AI can support a function but cannot hold formal office, vote or give final approval.

## When to expand beyond MVP governance / 何时扩展

Expansion should begin through an Issue that records a concrete operating problem. Useful signals include:

- four or more consistently active human contributors;
- multiple concurrent workstreams;
- recurring releases;
- a persistent triage or roadmap backlog;
- repeated appeals or conflicts of interest;
- specialist safety, ethics, language or method risks;
- Maintainer workload becoming a visible bottleneck.

Do not activate every role at once. Activate the smallest function that solves the recorded problem, set a review date and dissolve it when no longer needed.

## Optional functions / 可选职能

### Triage Steward / 议题管理员

Use when Issues and Discussions can no longer be reliably routed by the Maintainer alone.

Responsibilities may include:

- identifying duplicates and related work;
- proposing labels, states and dependencies;
- distinguishing Discussion, Issue, Proposal and Research;
- requesting missing context or evidence;
- maintaining a visible backlog.

AI may suggest triage but may not silently reject, close or lower the priority of significant contributions.

### Roadmap Steward or Council / 路线管理员或路线小组

Use when the project has multiple candidate goals and must make recurring resource choices.

Responsibilities may include:

- maintaining `Now / Next / Explore`;
- documenting dependencies and blockers;
- proposing milestones and stopping conditions;
- explaining why work is started, deferred or ended.

A council should normally have two to five human members. Popularity, English fluency and model-generated scores must not determine final priority.

### Temporary Working Group / 临时工作组

Use for a formal, time-bounded goal with clear deliverables.

A working-group record should define:

```yaml
title:
problem:
scope:
out_of_scope:
deliverables:
success_criteria:
owner:
required_review:
timebox:
dependencies:
stop_conditions:
```

The group dissolves when the work is accepted, stopped or transferred. A group lead cannot declare the group's output accepted.

### Reviewer Pool / 审查者池

Use when reviews recur often enough to require discoverable specialist availability.

Review dimensions may include:

```text
content · sources · method · language · security · ethics · governance · implementation
```

Reviewers state what they reviewed and what they did not. Major work should include at least one reviewer who did not draft it.

### Release Steward / 发布管理员

Use when Releases become recurring and version checks are a distinct workload.

Responsibilities may include:

- verifying version, status and metadata;
- checking superseded and deprecated links;
- preparing Release Notes;
- confirming that required review conditions are met;
- executing a previously approved Tag or Release.

The Release Steward checks readiness; they do not decide substantive acceptance.

### Ombudsperson or Appeal Panel / 程序监督员或申诉小组

Use when appeals, conflicts of interest or systematic participation barriers occur often enough that ad hoc external review is insufficient.

Possible scope:

- incorrect closure, routing or priority;
- language or identity barriers;
- systematic AI translation or classification failures;
- Maintainer or Reviewer conflicts of interest;
- omitted material objections;
- procedural non-compliance.

A temporary panel should contain humans not involved in the original decision. Its authority, scope and duration must be recorded.

## Activation record / 启用记录

Every activated function should have a public record:

```yaml
function:
problem_to_solve:
activated_at:
people:
powers:
limits:
conflict_rules:
review_date:
dissolution_condition:
appeal_path:
```

No role should exist only on paper. If the role has no active person or current need, mark it inactive.

## Scale examples / 规模示例

### MVP: one to three active humans

Active structure:

- one Maintainer;
- temporary human Reviewer per material change;
- external review for Maintainer conflicts or major rules;
- temporary working groups only when a real task needs one;
- simple Issue-based appeal.

This is the current Iris Commons model.

### Growing project: roughly four to ten active humans

Possible additions:

- rotating Triage Steward;
- small Roadmap group;
- discoverable Reviewer pool;
- temporary Working Groups;
- separate Release Steward when releases recur.

### Mature or high-impact project

Possible additions:

- Maintainer team;
- Roadmap Council;
- formal specialist review board;
- recurring Working Groups;
- Release function;
- independent appeal, ethics or safety panel.

These are examples, not required stages.

## Decision method / 决策方法

Expanded governance should still use:

> **rough consensus + recorded objections + reviewable decision**

A complex organization does not make model agreement, majority reactions or unrecorded private judgment authoritative.

## Template requirement / 模板项目最低公开内容

An independent project using this template should clearly state:

1. who maintains the repository;
2. how Issues are routed and prioritized;
3. who may initiate or stop formal work;
4. what requires independent human review;
5. who may merge and publish;
6. how self-approval and conflicts are prevented;
7. how appeals work;
8. what AI may and may not do.

Projects may use different names and structures. They should not pretend to have committees or review capacity that do not exist.
