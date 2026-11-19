# Dynamic Key Prompts 0.1.4 — Dark Souls III 1.15.0

Shows the **keyboard / mouse key you actually bound** instead of the gamepad button in prompts.

An unofficial port of Dynamic Key Prompts 0.1.4 to the 1.15.0 executable: upstream version 0.1.4, rebuilt for game version 1.15.0. **1.15.0 only.**

This repository holds the install-ready build.

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

## About this port

1.Two changes to 0.1.4: the loader detects the 1.15.0 executable and skips the upstream entry-point blocking (it used 1.15.2 addresses and crashed 1.15.0).

2.github.com/djlastnight/KeyboardSplitterXbox/releasesYou might need to use a virtual controller to set up some of the buttons, or some key prompts can not appear.

## Credits

Dynamic Key Prompts 0.1.4 by HappyEntity — MIT, see [LICENSE](LICENSE). MinHook and the Hacker Disassembler Engine are BSD 2-Clause — see [LICENSE-MinHook.txt](LICENSE-MinHook.txt). This port is unofficial and not affiliated with the author.
