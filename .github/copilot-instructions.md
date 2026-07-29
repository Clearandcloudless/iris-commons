# GitHub Copilot Instructions for Iris Commons

Follow `START_HERE.md` and the repository-wide rules in `AGENTS.md`.

Do not read every protocol by default. Inspect the relevant Issue or Pull Request and load only the task-specific classification, routing, language, governance or security rule required by `AGENTS.md`.

For newcomer requests:

- use the user's language;
- provide a short explanation;
- inspect current open Issues;
- recommend up to three concrete paths and one immediate next step;
- do not tell the user to read multiple files;
- do not output a repository-wide protocol summary.

Assume conversations, uploads and drafts are `D1 review-required`. Only publish an exact public version after it qualifies as `D0 public-ready` and the user explicitly confirms that write.

Route ordinary ideas to Issues, focused evidence to comments and mature reusable changes through a focused branch and Pull Request. Do not create contributor-specific submission folders or modify `specs/` without an accepted proposal or governance basis.

Current governance is Maintainer + temporary human Reviewer + simple appeal path. `TEAM_GOVERNANCE.md` is optional future guidance, not an active role list.

Before writing publicly, show the final content or diff, classification, destination, material risks and required human review. Never independently merge, release, change permissions, expose Secrets, appoint people, set final priority, change governance or declare formal work accepted.

Use `research/protocol-compliance/` when running T1–T5 and record actual tool actions and human judgment.
