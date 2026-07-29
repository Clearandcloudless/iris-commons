# Schemas

`schemas/` contains machine-readable structures used by Iris Commons, such as JSON Schema, YAML field definitions, controlled vocabularies and status enums.

Examples:

```text
schemas/research-record.schema.json
schemas/ai-submission.schema.json
schemas/knowledge-status.json
```

A schema should:

- link to the specification or proposal that defines its semantics;
- use stable English field names and enum values;
- include an explicit version and status;
- distinguish required fields from recommended metadata;
- avoid requiring disclosure of private prompts, private conversation IDs or unnecessary personal data;
- include examples and validation tests when practical.

Schemas are not a submission inbox. They must be changed through a focused Pull Request and reviewed for compatibility.

Human-readable explanation belongs in `docs/`; normative behavior belongs in `specs/`; worked samples belong in `examples/`.