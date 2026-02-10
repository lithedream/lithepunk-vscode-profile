# lithepunk-vscode-profile

A minimal VS Code setup tuned for fast navigation and low-friction editing.
Designed for Java work, but mostly language-agnostic.

## What this repo contains

- `profile/settings.json` — global editor/workbench defaults (theme, minimap off, sidebar right, terminal focus behavior) and Java specific configurations.
- `profile/keybindings.json` — custom navigation + symbol lookup workflow (`Alt+1..3` jump deck, `F3`, `F4`, etc.).

## Philosophy

- Language-agnostic global settings.
- Provide specific Java settings.
- Optimize for keyboard-driven code exploration and refactoring.

## Quick start

1. Copy `profile/settings.json` and `profile/keybindings.json` into your VS Code user profile.
2. Replace all `"..."` placeholders with JDK runtime paths.

## Expected extensions

For full keybinding behavior, install the [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack), since several keybindings invoke Java-specific commands.

I also suggest [XML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml) and a Markdown extension for quality of life.

## Keybinding map (high level)

The core of this setup is a small “jump deck” of navigation shortcuts that replaces most mouse-driven exploration.

- Jump deck core:
  - `Alt+1`: workspace symbols (project-wide symbol search)
  - `Alt+2`: Java extended outline on Java files, document symbols otherwise
  - `Alt+3`: quick open files/resources by name
- `F3`: go to definition
- `F4`: type hierarchy
- `Alt+A`: find references
- `Alt+Q`: show call hierarchy
- `Alt+E`: show all open editors
- `Alt+Z`: find in editor
- `Alt+Left` / `Alt+Right`: navigate back / forward
- `Ctrl+1`: quick fix
- `Ctrl+L`: go to line
- `Escape Escape`: toggle Zen mode

## Notes

This setup is an expression of my DX/DI (Developer Experience/Developer Interface) sensitivity. Adjust bindings/settings if you feel to.
