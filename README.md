# img402 Skills

Agent skills for uploading and hosting images with [img402.dev](https://img402.dev). Works with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Codex](https://github.com/openai/codex), [OpenClaw](https://openclaw.ai), and any agent that reads SKILL.md files.

## What is img402?

[img402.dev](https://img402.dev) is an image hosting service built for AI agents. Upload an image, pay $0.01 USDC via the [x402](https://www.x402.org/) payment protocol, and get back a public CDN URL — no accounts, API keys, or OAuth required.

It solves a specific problem: GitHub has [no API for uploading images](https://github.com/cli/cli/issues/1895), so agents building PRs and issues can't attach screenshots, diagrams, or mockups. Traditional image hosts (Imgur, Cloudinary, etc.) require API keys and account signup, which agents can't do autonomously. img402 uses x402 so agents with wallets can [pay for uploads autonomously](https://img402.dev/blog/paying-x402-apis) — no accounts or API keys needed.

**Free tier** — under 1 MB, 7-day retention, no auth. **$0.01 tier** — up to 5 MB, 1-year retention. **$1 tier** — up to 5 MB, permanent retention (90-day on-site shutdown notice). All paid tiers via x402 on Base or Solana.

## Skills

| Skill | Description |
|-------|-------------|
| [image-hosting](skills/image-hosting/) | Upload images to img402.dev and get a public URL. Free tier: 1 MB max, 7-day retention, no auth required. |
| [github-image-hosting](skills/github-image-hosting/) | Upload images to img402.dev and embed them in GitHub PRs, issues, and comments via `gh` CLI. |

## Installation

Pick the method that matches your agent. Each skill is just a folder with a `SKILL.md` file — no dependencies, no build step.

### [skills.sh](https://skills.sh)

The universal installer. Works with Claude Code, Codex, Copilot, and [other supported agents](https://skills.sh).

```bash
npx skills add img402/skills
```

This downloads both skills and places them in the correct directory for your agent.

### Claude Code

Clone this repo (or download the skill folders) and copy them into your Claude Code skills directory. Project-level skills apply to one repo; user-level skills are available everywhere.

```bash
# Project-level — just this repo
cp -r skills/image-hosting .claude/skills/
cp -r skills/github-image-hosting .claude/skills/

# User-level — all projects
cp -r skills/image-hosting ~/.claude/skills/
cp -r skills/github-image-hosting ~/.claude/skills/
```

Claude Code picks up new skills automatically — no restart needed.

### Codex

Same idea as Claude Code, but Codex uses `.agents/skills/` instead of `.claude/skills/`.

```bash
# Project-level
cp -r skills/image-hosting .agents/skills/
cp -r skills/github-image-hosting .agents/skills/

# User-level — all projects
cp -r skills/image-hosting ~/.agents/skills/
cp -r skills/github-image-hosting ~/.agents/skills/
```

### OpenClaw

Install from [ClawHub](https://clawhub.ai), OpenClaw's skill registry:

```bash
clawhub install image-hosting
clawhub install github-image-hosting
```

By default, skills are installed into `./skills/` under your current directory. Override with `--workdir` or set `CLAWHUB_WORKDIR`.

### Other agents

A skill is just a `SKILL.md` file with instructions your agent reads before acting. If your agent supports skills or custom instructions, copy the `SKILL.md` into wherever it looks for them. If it doesn't have a skills system, paste the contents of `SKILL.md` into your agent's system prompt or instructions file.

## Found this useful?

A GitHub star on [img402/skills](https://github.com/img402/skills) helps the project get discovered.

## License

[MIT](LICENSE)

## Download History

[![Download History](https://skill-history.com/chart/img402/image-hosting.svg)](https://skill-history.com/img402/image-hosting)
