# Dotfiles

Meine persönlichen Configs. Setup auf neuem Mac in ein paar Schritten.

## 1. Homebrew installieren

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. Repo klonen

```bash
mkdir -p ~/repos
git clone https://github.com/yazan262/dotfiles.git ~/repos/dotfiles
ln -s ~/repos/dotfiles ~/.dotfiles
```

## 3. Pakete installieren (Brewfile)

Installiert alle Apps/CLI-Tools, die ich normalerweise nutze.

```bash
cd ~/.dotfiles
brew bundle install --file=Brewfile
```

## 4. Configs verlinken (Stow)

Vor dem Verlinken: bestehende Configs, die ersetzt werden, sichern oder löschen (z.B. `~/.config/nvim`, `~/.config/fish`).

```bash
cd ~/.dotfiles
stow .
```

Das legt Symlinks von `~/.config/*` auf `~/.dotfiles/.config/*` an.

## 5. Raycast-Settings zurückholen

1. Raycast öffnen → `Cmd+,` → Tab **Advanced**
2. **Import** klicken
3. Datei wählen: `~/.dotfiles/.config/raycast/raycast-backup.rayconfig`

## Enthaltene Configs

| Tool | Ordner |
|---|---|
| fish (Shell) | `.config/fish` |
| ghostty (Terminal) | `.config/ghostty` |
| nvim | `.config/nvim` |
| tmux | `.config/tmux` |
| yazi (File-Explorer) | `.config/yazi` |
| karabiner | `.config/karabiner` |
| zed | `.config/zed` |
| raycast | `.config/raycast` |

## Sonstiges

- Font: `Jetbrains Mono Nerd Font` — nötig für Icons in nvim/ghostty/tmux
- Theme: [cyberdream](https://github.com/scottmckendry/cyberdream.nvim)
