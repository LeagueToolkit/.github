<!-- Title should follow Conventional Commits: feat: / fix: / docs: / chore: -->

## What and why

<!-- What changed, and what problem it solves. Link the issue: Closes #123 -->

## How it was tested

<!--
  Commands you ran, files you tested against, cases you covered.
  "cargo test" alone isn't an answer unless you added a test.
-->

## Checklist

- [ ] Title follows Conventional Commits (`feat:` / `fix:` / `docs:` / `chore:`; `!` for breaking)
- [ ] `cargo fmt --all -- --check` passes
- [ ] `cargo clippy -- -D warnings` passes
- [ ] `cargo test` passes
- [ ] README / docs updated if user-visible behavior changed
- [ ] Tests added for the bug fixed or feature added

<!-- Non-Rust repo? Delete the cargo lines. -->
