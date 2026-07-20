# LeagueToolkit/.github

Org-wide defaults. GitHub applies everything here to **every repository in the org that doesn't
ship its own copy** of the same file - no per-repo setup needed.

| File | Applies to |
| --- | --- |
| `profile/README.md` | The org profile page at [github.com/LeagueToolkit](https://github.com/LeagueToolkit) |
| `CONTRIBUTING.md` | Linked from the new-issue and new-PR pages of every repo |
| `CODE_OF_CONDUCT.md` | Shown in every repo's community profile |
| `SECURITY.md` | The **Security** tab / "Report a vulnerability" flow |
| `AI-STYLEGUIDE.md` | Reference only - not auto-applied. Linked from each repo's `AGENTS.md`. |
| `.github/ISSUE_TEMPLATE/*.yml` | The issue picker in every repo |
| `.github/ISSUE_TEMPLATE/config.yml` | Contact links shown alongside the templates |
| `.github/PULL_REQUEST_TEMPLATE.md` | Prefills every PR description |

A repo overrides any of these by adding its own file at the same path. Do that when the defaults
genuinely don't fit (a non-Rust repo, a different license) - not to make small wording tweaks.

Note that issue and PR templates must live under `.github/` here, while `CONTRIBUTING.md`,
`CODE_OF_CONDUCT.md`, and `SECURITY.md` are picked up from the repo root.

For starting a new repo, see [LeagueToolkit/repo-template](https://github.com/LeagueToolkit/repo-template).
