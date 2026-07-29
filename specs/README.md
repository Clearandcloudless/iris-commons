# Specifications

`specs/` contains the current normative protocols and implementation specifications of Iris Commons.

Use `specs`, not `standards`, while the project is still an open prototype. A document in this directory may define required behavior for compatible AI assistants, data formats or implementations, but it does not claim recognition by an external standards body.

A specification must normally have:

- an accepted proposal or recorded governance basis;
- a stable identifier and version;
- explicit status such as `draft`, `candidate` or `stable`;
- `normative: true` metadata;
- a clearly identified source language;
- compatibility and migration notes where relevant;
- human review through a focused Pull Request.

Suggested path:

```text
specs/ai-secretary-protocol/spec.md
```

Explanations and tutorials belong in `docs/`. Machine-readable constraints belong in `schemas/`. Historical revisions should normally be retrieved through Git history or Releases; only superseded documents that remain useful as standalone context belong in `archive/`.

AI must not create or modify a current specification and declare it accepted without the required human review.

See [`CONTENT_LIFECYCLE.md`](../CONTENT_LIFECYCLE.md).