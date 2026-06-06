# Distribution

Where these skills are published and how updates propagate.

## Channels

| Channel | URL | Mechanism | Auto-syncs from `main`? | Last verified |
|---------|-----|-----------|--------------------------|---------------|
| GitHub source | [img402/skills](https://github.com/img402/skills) | The repo itself | Yes (it _is_ the source) | live |
| skills.sh (Vercel-labs) | [skills.sh/img402](https://www.skills.sh/img402) | `npx skills add img402/skills` reads from GitHub | Yes — fetches the repo at install time | 2026-06-06 (66 installs) |
| ClawHub (OpenClaw) | `clawhub install image-hosting` / `github-image-hosting` | Registry stores a published snapshot (`name@semver`) | **No** — requires manual `clawhub publish` per release | 2026-02-10 (v1.0.0) |
| awesome-claude-skills (ComposioHQ) | [PR #177](https://github.com/ComposioHQ/awesome-claude-skills/pull/177) | Curated markdown list | **No** — listicle, doesn't track versions | PR opened 2026-02-10, still OPEN |

## Update propagation model

When you push a change to `main`:

- **GitHub**: instant.
- **skills.sh**: instant for new installs (the CLI pulls from the GitHub repo at install time). Existing installs need to be reinstalled.
- **ClawHub**: nothing happens until you run `clawhub publish` from each skill directory. Even then, existing installs are pinned to whatever version they got at install time — users need to run `clawhub update <skill>` or `clawhub update --all` to opt in. There is no auto-update channel.
- **awesome-claude-skills**: nothing happens. The PR text is what's listed; if the PR ever merges, that snapshot is what's permanently shown. No update mechanism.

## Publishing checklist (when shipping a new SKILL.md change)

1. Commit + push to `main` of `img402/skills`. GitHub + skills.sh are now updated for new installs.
2. Run `clawhub publish` from each skill directory to push the new version to ClawHub. Existing installs stay frozen until users opt in.
3. (Optional) Update the awesome-claude-skills PR description or post a comment noting the new tier / feature, in case it ever gets merged.

## Known propagation gaps

- **~1k existing ClawHub installs of v1.0.0** won't auto-update. The server-side `img402` response field is what reaches them in the meantime — it's a runtime hint that the API has new capabilities, not a code update.
- **awesome-claude-skills PR #177** has been open and unreviewed for 4+ months. Treat this distribution channel as effectively cold.
