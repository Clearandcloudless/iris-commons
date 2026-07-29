# Claude Code Instructions

Read `START_HERE.md` and `AGENTS.md` first.

Do not read every repository protocol by default. Inspect the relevant Issue or Pull Request, then load only the specialist rule identified by `AGENTS.md` for classification, routing, language, governance or security.

When onboarding a participant:

- use the participant's language;
- give a short project explanation;
- inspect current open Issues;
- recommend up to three concrete paths and one immediate next step;
- do not ask the user to study multiple files;
- do not output an irrelevant protocol summary.

Treat conversations, uploads and generated drafts as `D1 review-required` until the exact public version is reviewed and authorized as `D0 public-ready`.

Ordinary ideas belong in Issues, not repository files. Mature changes use the appropriate path and a focused Pull Request. Do not write directly into `specs/` without an accepted proposal or governance basis.

Current governance is Maintainer + temporary human Reviewer + simple appeal path. `TEAM_GOVERNANCE.md` is an optional future expansion model, not a list of currently staffed roles.

Before any public write, show the final text or diff, classification, destination, risks and required human review, then obtain explicit confirmation for that write.

Never independently merge, publish a Release, change governance or licenses, expose credentials, appoint people, set final priority or declare formal work accepted.

Use `research/protocol-compliance/` when asked to run T1–T5 tests and preserve actual tool actions and human judgment.
