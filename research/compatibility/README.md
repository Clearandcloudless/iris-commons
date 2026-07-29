# Demand-driven Compatibility / 需求驱动的兼容性清单

Status: `mvp-0.1`  
Related Issue: #5

Iris Commons will not delay real pilots until every open-science, knowledge-graph or federation standard has been compared.

MVP compatibility work is limited to three goals:

1. GitHub Issues, Pull Requests, Reviews and commits remain the auditable collaboration record.
2. Long-lived records preserve portable provenance, authorship, time, language and license metadata.
3. Project content can be exported as ordinary Markdown and JSON, with fields that can later map to established standards.

## Current non-goals / 当前不做

The MVP does not directly integrate:

- OSF;
- Zenodo;
- Dataverse;
- Wikibase;
- ActivityPub;
- DVC or lakeFS;
- a new Iris Commons federation protocol.

An integration should begin only when a real pilot produces a concrete need that cannot be met by a portable link, identifier or export.

## First mapping targets / 第一轮映射对象

The first round may examine at most:

- RO-Crate;
- DataCite metadata;
- W3C PROV-O.

The purpose is to identify field mappings and gaps, not to build complete integrations.

## Trigger-based workflow / 需求触发流程

When a pilot needs archiving, citation, provenance or cross-platform publication:

1. record the concrete requirement in an Issue;
2. select the smallest relevant external standard;
3. complete a one-page comparison using `mapping-template.md`;
4. decide `adopt`, `map`, `defer` or `reject` with reasons;
5. add only the minimum metadata or export change required by the pilot;
6. test that the repository remains usable without the external platform.

## Portable MVP fields / MVP通用字段

Long-lived records should be able to express:

```yaml
id:
type:
title:
status:
source_language:
created_at:
updated_at:
contributors:
origin:
sources:
license:
ai_assistance:
relations:
classification:
```

Exact schemas remain under development. Do not add a field solely because an external standard contains it; require a demonstrated project use.

## Decision log / 决策记录

Each comparison should conclude with:

```yaml
standard:
triggering_need:
decision: adopt | map | defer | reject
fields_used:
fields_not_used:
implementation_scope:
review_after:
related_issue:
```

Compatibility means that data can be mapped or exported. It does not require Iris Commons to depend on every external platform.
