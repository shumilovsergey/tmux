# micro — the editor

[micro](https://micro-editor.org) is "nano, but modern": non-modal, mouse-aware,
`Ctrl`-key shortcuts you already know, syntax highlighting built in (Go, Python,
YAML, ~130 more), and a real plugin system. This sets it up with a **file-tree
sidebar that opens automatically** — the VS Code look, in the terminal.

Config lives in **`~/.config/micro/`**.

---

## 1. Install

### macOS (Homebrew)
```sh
brew install micro
micro --version
```

### Linux (Debian / Ubuntu — apt)
```sh
sudo apt update
sudo apt install micro
micro --version
```
If apt's version is old, use snap or the official installer instead:
```sh
sudo snap install micro --classic
# or, no package manager:
cd ~ && curl https://getmic.ro | bash   # drops a `micro` binary you can move to /usr/local/bin
```

## 2. The file-tree plugin

Inside micro:
```
Ctrl-E                       (opens the command bar)
plugin install filemanager
```
Then **quit and reopen** micro (`Ctrl-Q`, then start it again) so it loads.

Open/close the tree by hand anytime with `Ctrl-E` then `tree`.

## 3. Make the tree open on every start + good defaults

Create/edit **`~/.config/micro/settings.json`**:
```json
{
    "filemanager-openonstart": true,
    "tabstospaces": true,
    "tabsize": 4,
    "mouse": true,
    "colorscheme": "monokai"
}
```
- `filemanager-openonstart` — the tree is there the moment micro starts.
- `tabstospaces` + `tabsize` — insert spaces, not tabs (YAML needs this; use `2` if you mostly write YAML).
- `colorscheme` — try `monokai`, `geany`, or `atom-dark` for dark terminals.

### Optional: a key to toggle the tree
Edit **`~/.config/micro/bindings.json`**:
```json
{ "Alt-t": "command:tree" }
```
(On macOS, `Alt` needs "Use Option as Meta key" in Terminal.app. No Meta? Use a
free `Ctrl-` key like `"Ctrl-b"` instead.)

---

## Using the file tree

| Key | Does |
|-----|------|
| `Tab` **or click** | open a file / expand-collapse a folder |
| `↑` `↓` | move up/down the list |
| `Shift-↑` | jump to the parent folder |
| `Ctrl-G` | help — shows the new / rename / delete keys |

> Files open in the split next to the tree. Some plugin versions open them in a
> new **tab** instead — cycle tabs with `Alt-,` / `Alt-.` if that happens.

### Narrowing the sidebar
The tree width is hardcoded (no setting): it starts at 30 columns and grows when
you expand nested folders. The plugin (channel build) sets it with `ResizePane(30)`
in several places, so change them all at once. Open the plugin file:
```sh
micro ~/.config/micro/plug/filemanager/filemanager.lua
```
Then run three replace commands (`Ctrl-E`, type, `Enter`):
```
replaceall "ResizePane(30)" "ResizePane(20)"
replaceall "Width < 30" "Width < 20"
replaceall "(30 + highest_visible_indent)" "(20 + highest_visible_indent)"
```
Save (`Ctrl-S`), restart micro. (`20` → pick any width you like.)

> A `micro -plugin update` can overwrite this — just redo the replaces. Keeping
> folders collapsed (`Tab` on an open folder) also stops the width from growing.

---

## Main editing shortcuts

### Files & app
| Key | Does |
|-----|------|
| `Ctrl-S` | save |
| `Ctrl-O` | open a file |
| `Ctrl-Q` | close this tab/split (last one = quit) |
| `Ctrl-E` | command bar |
| `Ctrl-G` | help |

### Edit
| Key | Does |
|-----|------|
| `Ctrl-Z` / `Ctrl-Y` | undo / redo |
| `Ctrl-C` / `Ctrl-X` / `Ctrl-V` | copy / cut / paste |
| `Ctrl-K` | cut the whole line |
| `Ctrl-D` | duplicate the line |
| `Tab` / `Shift-Tab` | indent / unindent |
| `Alt-↑` / `Alt-↓` | move the line up / down |

### Select
| Key | Does |
|-----|------|
| `Shift-←` / `Shift-→` | select by character |
| `Alt-Shift-←` / `Alt-Shift-→` | select by word |
| `Shift-Home` / `Shift-End` | select to start / end of line |
| `Ctrl-A` | select all |
| drag / double-click / triple-click | select range / word / line |

### Move & find
| Key | Does |
|-----|------|
| `Ctrl-←` / `Ctrl-→` | jump by word |
| `Home` / `End` | start / end of line |
| `Ctrl-Home` / `Ctrl-End` | start / end of file |
| `Ctrl-F` | find |
| `Ctrl-N` / `Ctrl-P` | next / previous match |

---

### Fastest start
`brew install micro` → open micro → `Ctrl-E`, `plugin install filemanager` →
restart → drop the `settings.json` above → the tree is waiting for you.
