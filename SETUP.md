# Development environment setup

Use this checklist when onboarding a machine or when an agent needs to (re)configure **Lua / Teardown API** support in Cursor or VS Code.

**Out of scope here:** installing Teardown itself, copying mods into the game’s mod folder—see each mod’s readme and official Teardown modding docs.

---

## 1. Editor extension (all OS)

1. Open Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`).
2. Install **Lua** by **sumneko** (extension id: `sumneko.lua`).
3. Reload the window if prompted.

---

## 2. LuaLS config: `.luarc.json`

- **Template:** [`.luarc.json.example`](.luarc.json.example) — placeholders for the Teardown **`data`** directory.
- **Working file:** `.luarc.json` at the repo root (gitignored). Copy from the example and fill paths for your OS (see below).
- **Required entries:** `runtime.plugin` → `td_vscode_plugin.lua`; `workspace.library` → `script_defs.lua`, `voxscript_defs.lua`, and `script/include` under the same `data` folder.

Use **forward slashes** in JSON paths (works on Windows and avoids escaping backslashes).

---

## Windows

### Default Teardown `data` path (Steam, default library)

`C:\Program Files (x86)\Steam\steamapps\common\Teardown\data`

If the game is on another Steam library drive, replace the prefix up to `\Teardown\data` accordingly.

### Verify the install (PowerShell)

Run from any directory:

```powershell
$data = "C:\Program Files (x86)\Steam\steamapps\common\Teardown\data"
@("script_defs.lua","voxscript_defs.lua","td_vscode_plugin.lua","script\include") | ForEach-Object {
  if (Test-Path -LiteralPath (Join-Path $data $_)) { "OK $_" } else { "MISSING $_" }
}
```

All lines should show `OK`. If anything is `MISSING`, fix the `$data` path before continuing.

### Example `.luarc.json` (Windows + default Steam path)

After copying `.luarc.json.example` to `.luarc.json`, set paths like:

```json
{
  "$schema": "https://raw.githubusercontent.com/LuaLS/vscode-lua/master/setting/schema.json",
  "runtime.version": "Lua 5.1",
  "runtime.plugin": "C:/Program Files (x86)/Steam/steamapps/common/Teardown/data/td_vscode_plugin.lua",
  "workspace.library": [
    "C:/Program Files (x86)/Steam/steamapps/common/Teardown/data/script_defs.lua",
    "C:/Program Files (x86)/Steam/steamapps/common/Teardown/data/voxscript_defs.lua",
    "C:/Program Files (x86)/Steam/steamapps/common/Teardown/data/script/include"
  ]
}
```

Adjust the `C:/Program Files (x86)/Steam/...` prefix if your `data` folder differs.

### Finish

Reload the editor window (or restart the Lua language server) so diagnostics and completions pick up Teardown definitions.

---

## Linux

*TBD — document typical install locations (e.g. Steam Linux `steamapps/common/Teardown/data`), path verification, and a sample `.luarc.json` once confirmed.*

---

## Agent quick sequence (Windows)

1. Confirm Teardown `data` exists and contains the four paths from the verification block above.
2. Ensure `.luarc.json` exists at repo root with `runtime.plugin` and `workspace.library` pointing at that `data` directory (use the example JSON shape).
3. Confirm `sumneko.lua` is installed; suggest reload if Lua features are missing.
