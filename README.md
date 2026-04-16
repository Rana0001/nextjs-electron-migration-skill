# Nextjs Electron Migration Skill

A universal skill for converting Next.js apps into production-ready Electron desktop applications.

## What this skill gives you

- Repeatable migration workflow (not one-off hotfixes)
- Secure Electron architecture (main/preload/renderer boundaries)
- Packaging strategy for macOS, Windows, and Linux
- CI pipeline structure and smoke-test guidance
- Release hardening checklist

## Who should use this

- Engineers migrating web-only Next.js apps to desktop
- Teams standardizing desktop architecture
- AI coding agents that need consistent migration guidance

## Compatibility

This skill is vendor-agnostic and works across coding agents/IDEs:

- Cursor
- VS Code agent extensions
- CLI agents
- Internal company agents

If auto-skill loading is unsupported, use this as prompt context manually.

## Installation (Cursor and other supported agents)

Install from GitHub into your current project:

```bash
npx skills add Rana0001/nextjs-electron-migration-skill --skill nextjs-electron-migration-skill
```

Install specifically for Cursor:

```bash
npx skills add Rana0001/nextjs-electron-migration-skill --skill nextjs-electron-migration-skill --agent cursor
```

Verify installation:

```bash
npx skills list
```

Expected skill name:

- `nextjs-electron-migration-skill`

## Troubleshooting install issues

- Use `npx skills ...` (not `npx skillsadd ...`).
- Use the exact skill name `nextjs-electron-migration-skill`.
- Check discovery from GitHub with:

```bash
npx skills add Rana0001/nextjs-electron-migration-skill --list
```

- If your environment has restricted temp directory permissions, retry from a normal local terminal with full filesystem permissions.
- Ensure Node.js and npm are available and updated.

## Example prompts

See `examples/prompts.md`.

## Versioning

Uses semantic versioning:

- MAJOR: breaking behavior changes
- MINOR: new capabilities
- PATCH: fixes and clarifications

## License

MIT
