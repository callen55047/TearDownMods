# AGENTS.md — TearDown Mods

**This file is the single source of context** for any model or agent working in this repository. Read it at the start of a task. Paste or attach its path when using assistants outside Cursor.

---

## Agent command — keep this file in sync

**Whenever your changes affect how the repo is organized or how future sessions should behave, update `AGENTS.md` in the same pass** (or immediately after), so prompting stays efficient and accurate.

Do that when you:

- Add, remove, or rename **top-level directories** or important subfolders under `mods/` or `ideas/`.
- Change **where** mods, assets, scripts, or docs are expected to live.
- Introduce **new conventions** (naming, manifests, Teardown version targets, build/install steps).
- Add **tooling** (scripts, package managers, CI) that agents should know about.
- Split or merge **mods** or **idea docs** in a way that changes the mental map of the tree.

**Do not** leave the tree and this document out of sync. If you only changed code inside one mod and nothing structural, you usually do not need to edit `AGENTS.md`.

---

## Directory map (canonical)

| Path | Role |
|------|------|
| **`AGENTS.md`** (this file) | Repo map, conventions, and maintenance rules for agents. |
| **`ideas/`** | Design documents for mod concepts. Not required to match shipped mods. Use descriptive `.md` names (e.g. `space-station.md`). |
| **`mods/`** | Runnable Teardown mod packages. **One subdirectory per mod** (e.g. `mods/my-mod/`) with manifest, Lua, assets, and a local readme when helpful. |
| **`SETUP.md`** | Lua / editor setup: LuaLS extension, `.luarc.json` from [`.luarc.json.example`](.luarc.json.example), OS-specific Teardown `data` paths (Windows documented; Linux TBD). |
| **`.cursor/rules/`** | Cursor-only rule snippets; keep them aligned with this file. |

Anything else at the repo root (e.g. `README.md`, `.gitignore`) is human-facing or tooling support; if it becomes relevant to **how agents should navigate or edit** the project, reflect that here.

---

## Project goal

1. **Ideas** — Capture mechanics, references, and open questions in `ideas/`.
2. **Implementation** — Ship mod code and assets under `mods/`.

**Multiplayer / co-op first** — Treat every idea and mod in this repo as **designed for multiple players working together** unless a doc explicitly scopes something else. Call out session size, host authority, and shared vs. per-player systems (suits, O₂, objectives) when it matters for implementation.

---

## Tech stack and assumptions

- **Teardown** mod gameplay logic is primarily **Lua**.
- Document **Teardown version** assumptions when APIs or layout differ by release.
- **Lua in the editor:** See [`SETUP.md`](SETUP.md) for LuaLS (`sumneko.lua`) and `.luarc.json` pointing at the game’s `data` API stubs.

---

## Conventions

- **Ideas**: Markdown; link out to games, videos, or docs when they clarify intent. Assume **co-op** as the default audience for gameplay notes.
- **Mods**: Self-contained folders under `mods/<name>/`; document install or symlink paths for the author’s platform in the mod readme when non-obvious.
- **Scope**: Prefer reusable helpers separate from map-specific or campaign-specific logic when it keeps the tree clear.

---

## Working style

- Read existing patterns in the target mod (or sibling ideas) before adding files.
- Prefer small, reviewable changes; avoid unrelated refactors.
- If the mod API is uncertain, use clear `TODO`s and note what must be verified in-game.

---

## Security (if you add tooling)

Follow secure coding practices for any Node, Python, or shell tooling: no user-controlled paths in file or process APIs, no secrets in source, validate external input.

---

## Cursor rules

[`.cursor/rules/`](.cursor/rules/) holds short Cursor rules. They should **mirror** this file, not duplicate long policy. If you change agent-facing structure here, update rules when needed.
