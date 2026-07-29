# Archive

`archive/` contains material that has left the active workflow but remains useful for historical, research or migration context.

Appropriate archive categories include:

```text
archive/withdrawn-proposals/
archive/superseded-specs/
archive/completed-pilots/
```

Do not copy every old version into this directory. Git history, tags and Releases are the primary source for ordinary version history.

Move content here only when it is no longer current as an active proposal, specification or pilot, but still deserves a stable standalone reference.

Archived documents should clearly state:

```yaml
status: superseded
archived_at: YYYY-MM-DD
superseded_by: specs/example/spec.md
```

AI must:

- search current `specs/`, `decisions/` and governance before the archive;
- identify archived status when citing material;
- never present an archived specification as current guidance;
- preserve links between archived and replacement content.

Archiving does not make sensitive information safe. Only `D0 public-ready` material may enter this public directory.