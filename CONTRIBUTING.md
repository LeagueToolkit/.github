# Contributing to LeagueToolkit

Thanks for wanting to help. This guide applies to every repository in the
[LeagueToolkit](https://github.com/LeagueToolkit) org unless that repo ships its own
`CONTRIBUTING.md`.

## Before you start

- **Open an issue first for anything non-trivial.** A bug fix or a typo can go straight to a PR.
  A new subcommand, a format change, or a refactor should start as an issue so we can agree on the
  shape before you spend time on it.
- **Check the existing issues.** Someone may already be on it.
- **One PR, one concern.** A PR that fixes a bug *and* reformats the file is hard to review and
  hard to revert.

## Development setup

Most of our tooling is Rust. You'll need a recent toolchain - check the repo's
`rust-toolchain.toml` or its README, since some projects need nightly.

```bash
git clone https://github.com/LeagueToolkit/<repo>.git
cd <repo>

rustup component add rustfmt clippy
cargo build
cargo test
```

Before you push:

```bash
cargo fmt --all -- --check
cargo clippy -- -D warnings
cargo test
```

CI runs the same three checks on Linux, Windows, and macOS. Running them locally saves a round trip.

## Code style

- **Match the surrounding code.** Naming, comment density, error handling, module layout - the
  local convention wins over your personal preference.
- **`rustfmt` decides formatting.** Don't hand-format, don't add `#[rustfmt::skip]` without a
  reason in a comment.
- **No new `clippy` warnings.** If a lint is genuinely wrong for your case, `#[allow]` it with a
  comment explaining why.
- **Errors carry context.** Prefer typed errors (`thiserror`) in libraries and `anyhow`-style
  context at the binary edge. An error a user sees should tell them which file and which field.
- **Public items get doc comments**, especially in the parsing libraries where the format itself
  needs explaining.

## Commits and PRs

We use [Conventional Commits](https://www.conventionalcommits.org/) - several repos derive their
changelogs and version bumps from them via `release-plz`, so the prefix matters:

```
feat: add --full-bin-scan to the paths command
fix: handle zero-length chunks when extracting
docs: document the hashtable precedence order
chore: bump league-toolkit to 0.9
```

`feat` triggers a minor bump, `fix` a patch. A `!` after the type (`feat!:`) or a
`BREAKING CHANGE:` footer triggers a major bump - use it deliberately.

In the PR description, say **what changed and why**. Link the issue it closes. If behavior a user
can observe changed, update the README in the same PR.

## Tests

- Add a test with every bug fix - the test should fail before your change and pass after.
- New parsing or format code needs round-trip coverage (read → write → read).
- Real game files can't be committed. Construct fixtures in code, or check in a minimal
  hand-crafted sample.

## Reverse-engineering contributions

Much of this org is reverse-engineered file formats. If you're adding format knowledge:

- **Document what you know and flag what you're guessing at.** A field named `unknown_0x14` with a
  comment describing what values you've observed is more useful than a confidently wrong name.
- **Say where the knowledge came from** - a game version, a binary offset, a related project.
  Format details drift between patches and the next person needs to know what your finding was
  based on.
- Don't commit game assets or binaries.

## Reporting bugs

Use the issue templates. The three things that make a bug actionable: the **exact command** you
ran, the **full error output**, and the **game version / file** involved (a link, not the file
itself, if it's a game asset).

## Security

Don't open a public issue for a security problem - see
[SECURITY.md](https://github.com/LeagueToolkit/.github/blob/main/SECURITY.md).

## Licensing

Contributions are licensed under the same terms as the repository you're contributing to. Check
its `LICENSE` file - the org is a mix of GPL-3.0, MIT, and dual MIT/Apache-2.0.
