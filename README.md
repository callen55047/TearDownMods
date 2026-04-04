# TearDown Mods

A single repository for **Teardown** mod work: design notes, concepts, and shipping mod implementations. **Ideas and mods here target multiplayer / co-op** unless stated otherwise.

## Layout

| Path | Purpose |
|------|---------|
| [`ideas/`](ideas/) | Concept write-ups (co-op–first), mechanics notes, and references before or alongside implementation. |
| [`mods/`](mods/) | Actual mod packages: scripts, assets, manifests, and anything needed to run in-game. |
| [`AGENTS.md`](AGENTS.md) | Single source of context for AI agents: layout, conventions, and when to refresh it after structural changes. |

## Teardown modding (quick reference)

Teardown mods are typically built from **Lua** scripts, game assets, and the mod layout expected by the game. Exact file layout depends on your target Teardown version and whether you use official examples or community tooling.

When adding a new mod under `mods/`, prefer a self-contained folder per mod (name, `info.txt` or equivalent manifest, scripts, and assets) and document build or install steps in that mod’s readme.

## Ideas

New concepts live in `ideas/` as markdown. See [`ideas/space-station.md`](ideas/space-station.md) for the first concept.

## License

Specify a license when you publish; until then, treat contents as private unless you state otherwise.
