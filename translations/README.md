# Translations

`translations/` contains maintained translations of governance documents, specifications and long-form guides when language-specific files beside the source are no longer sufficient.

README language variants may remain at the repository root, for example:

```text
README.zh-CN.md
README.ja.md
README.fr.md
```

Long-form translations should mirror the source structure where practical:

```text
translations/zh-CN/specs/ai-secretary-protocol.md
translations/ja/governance/language-policy.md
```

Each translated file should identify:

```yaml
translation_of: specs/example/spec.md
source_commit: abc1234
source_language: en
target_language: zh-CN
translation_method: ai
translation_status: machine-generated
human_reviewed: false
```

Translations are derived views. They must not silently change normative meaning or replace a participant's original-language expression.

Outdated translations must be marked `outdated` and link to the current source. See [`LANGUAGE_POLICY.md`](../LANGUAGE_POLICY.md).