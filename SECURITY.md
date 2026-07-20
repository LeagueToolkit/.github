# Security Policy

## Reporting a vulnerability

**Please don't open a public issue for a security vulnerability.**

Report it privately through GitHub's
[private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability):
go to the affected repository → **Security** tab → **Report a vulnerability**.

Include what you'd want to receive: the affected repo and version, what an attacker can do, and
the smallest set of steps that reproduces it.

We'll acknowledge the report and let you know whether we're treating it as a vulnerability and
roughly when to expect a fix. If you want credit in the advisory, say so.

## Scope

Our tools parse untrusted binary files - WADs, `.bin`, textures, manifests - and several register
Windows shell extensions. Things we consider security issues:

- Memory-safety bugs or panics-as-DoS reachable from a malformed input file
- Path traversal during extraction (a chunk writing outside the output directory)
- Privilege escalation in installers or shell/thumbnail-handler registration
- Code execution triggered by opening, previewing, or thumbnailing a file

Things we generally don't:

- Crashes on inputs you deliberately corrupted with no path to anything worse than a crash
- Issues in League of Legends itself - report those to
  [Riot](https://hackerone.com/riot), not here
- Anything requiring the attacker to already have code execution on the machine

## Supported versions

We patch the latest release. If you're on an older version, upgrade first and check whether the
issue still reproduces.
