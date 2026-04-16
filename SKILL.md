---
name: nextjs-electron-migration
description: Migrate Next.js applications to production-ready Electron desktop apps with secure IPC, packaging, CI, and release hardening.
version: 1.0.0
author: Prashant Rana Magar
license: MIT
tags: [nextjs, electron, desktop, migration, ipc, security, packaging, ci]
compatibility: universal
---

# Nextjs Electron Migration

## Compatibility

This skill is designed to work across coding agents and IDEs:

- Works as plain Markdown guidance if frontmatter is ignored
- No dependency on agent-specific internal tools
- Commands are standard shell/npm workflows
- Can be used manually by copying sections into prompts

## Purpose

Convert any Next.js application into a secure, maintainable, production-ready Electron desktop app using a repeatable migration workflow.

## Use This Skill When

- User asks to convert Next.js app to desktop app
- User needs Electron integration with Next.js
- User asks for secure preload + IPC architecture
- User needs desktop packaging and CI setup
- User wants migration checklist and rollout plan

## Core Principles

1. Preserve Next.js renderer architecture.
2. Keep Electron preload bridge minimal and explicit.
3. Enforce secure BrowserWindow defaults.
4. Standardize scripts for dev/build/dist/smoke.
5. Validate via security, lifecycle, packaging, and CI gates.

## Target Architecture

- `electron/main.(js|ts)` for app lifecycle, windows, native integrations, and IPC handlers
- `electron/preload.(js|ts)` for secure API exposure via `contextBridge`
- `src/...` for Next.js renderer (existing app)
- Optional `src/lib/desktop/client.(ts|js)` adapter to abstract `window.desktopAPI`

## Migration Workflow

1. Audit existing Next.js app (SSR, API routes, env, assets)
2. Add Electron main and preload files
3. Define renderer loading strategy:
   - Dev: load `next dev` URL
   - Prod: spawn `next start` or use static export strategy when compatible
4. Implement minimal IPC contracts (`desktop:get-app-version`, `desktop:shell:open-external`)
5. Add desktop persistence (`electron-store`) for window state/preferences
6. Add packaging with `electron-builder`
7. Add smoke tests and CI matrix (macOS/Windows/Linux)
8. Harden navigation controls and lifecycle shutdown behavior

## Security Baseline (Required)

- `contextIsolation: true`
- `nodeIntegration: false`
- `sandbox: true`
- Strict preload API whitelist
- IPC input validation in main process
- `setWindowOpenHandler` for external links
- `will-navigate` allowlist
- Never expose raw Node APIs to renderer

## Output Format

When this skill is used, return:

1. Migration scope and assumptions
2. Architecture decisions
3. File and script changes plan
4. Security hardening plan
5. Build/packaging plan
6. Test and CI strategy
7. Risks and mitigations
8. Definition of done

## Definition of Done

- Desktop app launches in dev and production modes
- IPC bridge works for at least one validated native capability
- Navigation and external-link policies enforced
- Packaging succeeds for target platforms
- Smoke tests pass in CI
- Release checklist completed
