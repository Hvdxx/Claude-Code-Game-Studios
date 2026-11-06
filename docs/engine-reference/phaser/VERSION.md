# Phaser — Version Reference

| Field | Value |
|-------|-------|
| **Engine Version** | Phaser 4.2.1 |
| **Installed at pin time** | 4.2.1 — npm `latest` tag, checked with `npm view phaser` on 2026-11-06; installed per project via `package.json` |
| **Release Date** | 4.2.1: 2026-07-09 (npm publish time) |
| **Project Pinned** | 2026-11-06 |
| **Last Docs Verified** | 2026-11-06 (version and release dates only) |
| **Risk Level** | HIGH — Phaser 4.0 shipped 2026-04-10; most training data covers Phaser 3 |

## Knowledge Gap Warning

Phaser 4 is a major version released in April 2026. Most code examples the
model has seen are Phaser 3 (frozen at 3.90.0). Phaser 4 keeps much of the
Phaser 3 API, but its renderer was rewritten and some APIs changed.

Rules for agents:
- Do not assume a Phaser 3 API exists unchanged in Phaser 4. Check the
  official docs or the installed package's type definitions
  (`node_modules/phaser/types/`) before relying on one.
- Every change that players can see is verified by running the game in a real
  browser (Playwright + Chromium) and keeping a screenshot.
- Breaking-change and best-practice notes are NOT SOURCEABLE yet — none were
  fetched this run. Add them here, with the URL they came from, as they are found.

## Release timeline (from npm publish times)

| Version | Published |
|---------|-----------|
| 4.0.0 | 2026-04-10 |
| 4.1.0 | 2026-04-30 |
| 4.2.0 | 2026-06-19 |
| 4.2.1 | 2026-07-09 |

## Sources

- https://phaser.io/download/release/v4.2.0
- https://phaser.io/download/release/v4.1.0
- https://phaser.io/download/stable
- `npm view phaser time` (2026-11-06)
