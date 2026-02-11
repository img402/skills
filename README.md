# img402 Skills

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills for uploading and hosting images with [img402.dev](https://img402.dev).

## Skills

| Skill | Description |
|-------|-------------|
| [image-hosting](skills/image-hosting/) | Upload images to img402.dev and get a public URL. Free tier: 1 MB max, 7-day retention, no auth required. |
| [github-image-hosting](skills/github-image-hosting/) | Upload images to img402.dev and embed them in GitHub PRs, issues, and comments via `gh` CLI. |

## Installation

Add a skill to your project:

```bash
claude skill add --from img402/skills/skills/image-hosting
claude skill add --from img402/skills/skills/github-image-hosting
```

## License

[MIT](LICENSE)
