# Dynamic Key Prompts 0.1.4 — Dark Souls III 1.15.0

**English** · [中文](#中文)

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
| `Diagnostics` | `1` = more detailed `DynamicKeyPrompts.log` |

## About this port

1.Two changes to 0.1.4: the loader detects the 1.15.0 executable and skips the upstream entry-point blocking (it used 1.15.2 addresses and crashed 1.15.0).

2.github.com/djlastnight/KeyboardSplitterXbox/releasesYou might need to use a virtual controller to set up some of the buttons, or some key prompts can not appear.

## Credits

Dynamic Key Prompts 0.1.4 by HappyEntity — MIT, see [LICENSE](LICENSE). MinHook and the Hacker Disassembler Engine are BSD 2-Clause — see [LICENSE-MinHook.txt](LICENSE-MinHook.txt). This port is unofficial and not affiliated with the author.

---

## 中文

[English](#dynamic-key-prompts-014--dark-souls-iii-1150) · **中文**

把提示里的手柄按键换成**你实际绑定的键鼠按键**。

这是 Dynamic Key Prompts 0.1.4 针对游戏版本 1.15.0 重新编译的非官方移植版：上游版本 0.1.4，按 1.15.0 的可执行文件重新编译。**仅支持 1.15.0。**

本仓库提供可直接安装的成品。

## 安装

把下面两样放到 `DarkSoulsIII.exe` 旁边（`...\DARK SOULS III\Game\`），然后从 Steam 正常启动游戏：

```
Game\xinput1_3.dll
Game\DynamicKeyPrompts\DynamicKeyPrompts.dll
Game\DynamicKeyPrompts\DynamicKeyPrompts.ini
```

**卸载：** 删掉 `xinput1_3.dll` 和 `DynamicKeyPrompts` 文件夹。
若 `xinput1_3.dll` 已被别的 mod 占用，两者无法共存。

## 设置

`DynamicKeyPrompts\DynamicKeyPrompts.ini`：

| 项 | 取值 |
|---|---|
| `Enabled` | `0` = mod 完全不生效 |
| `Style` | `text` = 用文字显示键名，如 `[E]` · `icons` = 显示按键图标（缓存写在 `DynamicKeyPrompts\cache\ds3`） |
| `IconTheme` | 图标外观：`dark` / `minimal` / `silver` |
| `Labels` | 某个操作同时有按键和鼠标键时显示哪个：`auto` / `keyboard` / `mouse` / `both` |
| `Format` | 仅文字模式；`{0}` 是键名，例如 `[{0}]` → `[E]` |
| `Separator` | 同一摇杆 / 十字键提示里多个键之间的分隔符 |
| `Color` | 键名颜色 `RRGGBB`，留空 = 跟随正常文字颜色 |
| `Diagnostics` | `1` = `DynamicKeyPrompts.log` 记录更详细的日志 |

## 关于此移植

1.相对 0.1.4 改了两处：加载器会识别 1.15.0 的可执行文件，跳过上游的入口点屏蔽（上游用的是 1.15.2 的地址，在 1.15.0 上会直接崩溃） 。

2.github.com/djlastnight/KeyboardSplitterXbox/releases 可能需要借助虚拟手柄设置一些按键，否则一些按键提示词不会显示。



## 致谢

Dynamic Key Prompts 0.1.4 作者 HappyEntity — MIT 许可，见 [LICENSE](LICENSE)。MinHook 与 Hacker Disassembler Engine 为 BSD 2-Clause 许可 — 见 [LICENSE-MinHook.txt](LICENSE-MinHook.txt)。本移植为非官方版本，与原作者无关联。
