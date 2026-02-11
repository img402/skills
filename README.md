# img402 Skills

Agent skills for uploading and hosting images with [img402.dev](https://img402.dev). Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Codex](https://github.com/openai/codex), [OpenClaw](https://openclaw.ai), and any agent that reads SKILL.md files.

## Skills

| Skill | Description |
|-------|-------------|
| [image-hosting](skills/image-hosting/) | Upload images to img402.dev and get a public URL. Free tier: 1 MB max, 7-day retention, no auth required. |
| [github-image-hosting](skills/github-image-hosting/) | Upload images to img402.dev and embed them in GitHub PRs, issues, and comments via `gh` CLI. |

## Installation

### [skills.sh](https://skills.sh)

```bash
npx skills add img402/skills/image-hosting
npx skills add img402/skills/github-image-hosting
```

### Claude Code

```bash
claude skill add --from img402/skills/image-hosting
claude skill add --from img402/skills/github-image-hosting
```

### Codex

Copy the skill folder into `.agents/skills/` (project-level) or `~/.agents/skills/` (user-level):

```bash
# Project-level
cp -r skills/image-hosting .agents/skills/

# User-level (available in all projects)
cp -r skills/image-hosting ~/.agents/skills/
```

### OpenClaw

```bash
clawhub install image-hosting
clawhub install github-image-hosting
```

### Manual

Copy the `SKILL.md` file into your agent's skills directory. The skill is a single file with no dependencies.

## License

[MIT](LICENSE)
