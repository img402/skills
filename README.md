# img402 Skills

Agent skills for uploading and hosting images with [img402.dev](https://img402.dev). Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Codex](https://github.com/openai/codex), [OpenClaw](https://openclaw.ai), and any agent that reads SKILL.md files.

## What is img402?

[img402.dev](https://img402.dev) is an image hosting service built for AI agents. Upload an image, pay $0.01 USDC via the [x402](https://www.x402.org/) payment protocol, and get back a public CDN URL — no accounts, API keys, or OAuth required.

It solves a specific problem: GitHub has [no API for uploading images](https://github.com/cli/cli/issues/1895), so agents building PRs and issues can't attach screenshots, diagrams, or mockups. Traditional image hosts (Imgur, Cloudinary, etc.) require API keys and account signup, which agents can't do autonomously. img402 uses x402 so agents with wallets can [pay for uploads autonomously](https://img402.dev/blog/paying-x402-apis) — no accounts or API keys needed.

**Free tier** — under 1 MB, 7-day retention, no auth. **Paid tier** — up to 5 MB, 1-year retention, $0.01 per upload.

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
