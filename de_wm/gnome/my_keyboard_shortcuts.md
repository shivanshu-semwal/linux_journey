# Keyboard Shortcuts

## Changing using `dconf-editor`

### For changing workspaces

```sh
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-1 "['<Super>1']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-2 "['<Super>2']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-3 "['<Super>3']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-4 "['<Super>4']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-5 "['<Super>5']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-6 "['<Super>0']"
```

### For moving applications to workspaces

```sh
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-1 "['<Shift><Super>1']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-2 "['<Shift><Super>2']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-3 "['<Shift><Super>3']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-4 "['<Shift><Super>4']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-5 "['<Shift><Super>5']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-6 "['<Shift><Super>0']"
```

### Other shortcuts

```sh
dconf write /org/gnome/desktop/wm/keybindings/close "['<Shift><Super>q']"
dconf write /org/gnome/desktop/wm/keybindings/maximize "['<Super>Up']"
dconf write /org/gnome/desktop/wm/keybindings/move-to-workspace-last "['<Shift><Super>parenright']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-last "['<Super>0']"
```