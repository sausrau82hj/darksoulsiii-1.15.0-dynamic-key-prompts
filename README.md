# Dynamic Key Prompts 0.1.4 — *Dark Souls III 1.15.0*

Shows the **keyboard / mouse key you actually bound** instead of the gamepad button in prompts.

An unofficial port of Dynamic Key Prompts 0.1.4 to the 1.15.0 executable. **1.15.0 only.** This repository holds the install-ready build and the source of the files that differ from upstream.

## Install

Copy both items next to `DarkSoulsIII.exe` (`...\DARK SOULS III\Game\`), then start the game from Steam:

```
Game\xinput1_3.dll
Game\DynamicKeyPrompts\DynamicKeyPrompts.dll
Game\DynamicKeyPrompts\DynamicKeyPrompts.ini
```

**Uninstall:** delete `xinput1_3.dll` and the `DynamicKeyPrompts` folder.
If another mod already occupies `xinput1_3.dll`, the two cannot be installed together.

## Settings

`DynamicKeyPrompts\DynamicKeyPrompts.ini`:

| Key | Values |
|---|---|
| `Enabled` | `0` = the mod does nothing |
| `Style` | `text` = key names as text, e.g. `[E]` · `icons` = key icons (cached in `DynamicKeyPrompts\cache\ds3`) |
| `IconTheme` | icon look: `dark` / `minimal` / `silver` |
| `Labels` | when an action has both a key and a mouse button: `auto` / `keyboard` / `mouse` / `both` |
| `Format` | text only; `{0}` is the key name, e.g. `[{0}]` → `[E]` |
| `Separator` | between the keys of a stick / d-pad prompt |
| `Color` | key label colour `RRGGBB`, empty = normal text colour |
| `Diagnostics` | `1` = verbose diagnostics |

## Source

Upstream is [Dynamic Key Prompts](https://github.com/HappyEntity/Souls-Dynamic-Key-Prompts) at tag `ds3-v0.1.4`, MIT. This port replaces three of its files:

- `src/Games/Ds3/Rva.cs` — the address table relocated to the 1.15.0 executable; the 1.15.2 values are kept as comments.
- `src/Games/Ds3/KeyIcons.cs` — icon carrier `menu/01_common.tpf.dcx`, which is the texture pack 1.15.0 loads (1.15.2 uses `05_dummy`).
- `src/Loader/dllmain.cpp` — dearxan's entry-point blocking uses 1.15.2 addresses and crashes 1.15.0, so the loader detects the 1.15.0 executable and starts without dearxan.

Build:

```
git clone --branch ds3-v0.1.4 https://github.com/HappyEntity/Souls-Dynamic-Key-Prompts
# copy the three files above over the same paths, then:
pwsh .\build.ps1 -Game ds3
```

Requires Visual Studio 2026 with the C++ desktop workload and the .NET 10 SDK; `build.ps1` downloads dearxan on first run. Output goes to `out\ds3`. Built from these three files, both DLLs match the ones in this repository (`.text`, `.data`, `.pdata`, `.reloc` identical).

## Notes

Setting up some of the buttons may need a virtual controller, otherwise those key prompts cannot appear — [KeyboardSplitterXbox](https://github.com/djlastnight/KeyboardSplitterXbox/releases) is one way.

## Credits

Dynamic Key Prompts 0.1.4 by HappyEntity — MIT, see [LICENSE](LICENSE). The loader includes dearxan, MinHook and the Hacker Disassembler Engine — licenses in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) and [LICENSE-MinHook.txt](LICENSE-MinHook.txt). This port is unofficial and not affiliated with the author.
