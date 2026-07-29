# Language Policy / 语言规则

Status / 状态：`draft-0.2`

Iris Commons does not require participants to use one shared language. The policy has three simultaneous goals:

- people can express ideas in the language in which they think most accurately;
- AI assistants and software can parse, exchange and migrate project data reliably;
- original text, translations, summaries and normative specifications remain clearly distinguishable and traceable.

## 1. Core principle / 总体原则

> **English for interoperability; native languages for thought.**  
> **英文负责互操作，母语负责思想表达。**

This means:

- human discussion is not restricted by language;
- stable machine-readable identifiers use English;
- translation connects languages but never replaces the original;
- an English bridge summary may improve discoverability but is not a condition of participation;
- fluency in English must never be treated as evidence that an idea is more credible.

## 2. Language layers / 内容语言分层

### 2.1 Original human expression

Issues, comments, proposals, interview records and research ideas may use any language.

The participant's original expression is the authoritative record of that participant's intent. AI or other contributors must not preserve only a rewritten, summarized or translated version while deleting the original.

### 2.2 Translations and summaries

Translations and summaries are derivative content. Where appropriate, record:

```yaml
source_language: zh-CN
target_language: en
translation_method: ai
translation_provider: OpenAI
translation_model: model-name-or-unknown
human_reviewed: false
source_reference: issue-or-file-reference
source_revision: commit-or-timestamp
```

Machine translation must be identified. Terms that cannot be translated accurately should retain the original wording with an explanation.

A translation must not:

- turn a question into a fact;
- turn a tentative inference into a definite conclusion;
- remove minority views, uncertainty or limiting conditions;
- replace the source meaning with a culturally more convenient position;
- claim perfect semantic equivalence without author confirmation.

### 2.3 Technical specifications

For protocols, schemas, APIs, state enumerations and implementation requirements, the long-term model is:

- the English version is the normative protocol version;
- other languages are explicitly linked translations;
- each translation records its source file, source commit and synchronization status;
- implementation conflicts are resolved by the version marked `normative`.

This rule governs software and protocol semantics only. It does not change the authoritative language of a participant's original ideas.

Many current design documents were initially drafted in Chinese and remain valid drafts. English normative versions will be established gradually through reviewed Pull Requests.

## 3. Machine identifiers / 机器标识

The following use stable English names or established English-compatible formats:

- repositories, branches, directories and filenames;
- YAML, JSON and form field IDs;
- API parameters and schema properties;
- labels;
- status, type and role enumerations;
- commit type prefixes;
- tool and protocol identifiers.

Example:

```yaml
record_type: proposal
source_language: zh-CN
translation_status: machine-generated
knowledge_status: discussing
human_reviewed: true
```

User-facing labels and descriptions may be multilingual, but stable IDs must not change with the interface language.

## 4. README language model / README语言模式

The repository uses English as the default public entry language:

```text
README.md          English default
README.zh-CN.md    Simplified Chinese
README.ja.md       Japanese
README.ko.md       Korean
README.fr.md       French
README.de.md       German
README.ru.md       Russian
```

Rules:

- every README begins with the same language selector;
- `README.md` is the source version for the public project introduction;
- localized READMEs communicate the same project identity and participation invitation;
- README files are promotional entry pages, not normative protocol documents;
- translation differences must not silently change project governance or technical requirements;
- language improvements and native-speaker review are welcome through Pull Requests;
- additional languages may be added when a contributor can maintain or review them.

The complete AI participation workflow remains in `AI_PARTICIPATION.md`. AI discovery and behavior requirements remain in `AGENTS.md` and client-specific instruction files. Formal technical material belongs in `docs/` or a future `specs/` directory.

## 5. Issues and Discussions / 议题与讨论

- any language may be submitted directly;
- form field IDs use English;
- user-facing field names may be bilingual or localized;
- `source_language` is required for structured submissions;
- an English summary is recommended but optional;
- AI may generate bridge summaries when useful;
- an Issue must not be closed or deprioritized merely because it lacks English content.

Recommended structure for substantive cross-language records:

```markdown
## Original

The participant's original content.

## Bridge summary

An optional English or other bridge-language summary.

## Translation notes

Terminology, context, ambiguity and review status.
```

Short comments do not need to repeat this structure mechanically. It becomes important for formal proposals, semantic disputes and cross-language review.

## 6. Pull Requests

A PR involving multilingual content should state:

- `source_language`;
- whether translations are included;
- the translation method;
- which version, if any, is normative;
- whether the author or a reviewer confirmed key semantics;
- whether AI assisted with translation, drafting or review.

A translation-only PR must not silently change normative meaning.

## 7. AI assistant behavior / AI助手行为

AI assistants must:

1. communicate with the user in the user's current language;
2. never require the user to translate into English before participating;
3. preserve the user's original expression;
4. use English for stable machine fields, paths and labels;
5. distinguish original text, translation, summary and inference in public submissions;
6. ask the author or mark uncertainty when translation is ambiguous;
7. never treat fluent English as a credibility signal;
8. provide bridge summaries and terminology notes when cross-language participation requires them;
9. disclose AI translation or rewriting roles;
10. never present an AI rewrite as the user's exact words.

## 8. Language codes

Use BCP 47-style language tags where structured metadata is required:

```text
en
zh-CN
zh-TW
ja
ko
fr
de
ru
es
ar
```

Use `und` when the language cannot yet be determined. Do not use only vague values such as `foreign`, `Chinese` or `other` when a more precise tag is available.

## 9. Translation status

Recommended values:

- `machine-generated`: generated by a machine and not yet linguistically reviewed;
- `human-reviewed`: reviewed by a human language user;
- `author-confirmed`: key meaning confirmed by the original author;
- `outdated`: the source has changed;
- `partial`: only part of the source is translated;
- `withdrawn`: no longer used because of serious errors.

## 10. Conflict handling

### Participant intent

Use the participant's original-language content as the primary evidence of intent and invite the author to confirm disputed meaning.

### Protocol implementation

Use the version and commit explicitly marked `normative`.

### Outdated translation

Do not silently display it as current. Mark it `outdated` and link to the source version.

## 11. Current transition plan

1. Keep existing Chinese design drafts available.
2. Use English for all new machine identifiers.
3. Maintain English as the default README and synchronized localized entry pages.
4. Keep Issue and PR forms multilingual in presentation and English in stable IDs.
5. Prioritize English versions of AI onboarding, governance and core protocols.
6. Add checks for missing language fields, broken README navigation and outdated translations.
7. Revise this policy using evidence from real cross-language pilot projects.

This language policy must itself be reviewed by participants from different language communities. It must not be determined only by English or Chinese speakers.