# lithepunk-vscode-profile

A minimal VS Code setup tuned for fast navigation and low-friction editing, attuned to Java but mostly language-agnostic.
Built for me, and for the lost souls of Eclipse developers who want to feel at home in VS Code.

## What this repo contains

- `profile/settings.json` — global editor/workbench defaults (theme, minimap off, sidebar right, terminal focus behavior).
- `profile/keybindings.json` — custom navigation + symbol lookup workflow (`Alt+1..3` jump deck, `F3`, `F4`, etc.).
- `profile/java.code-workspace` — **workspace template** for Java projects (JDK runtimes, source paths, Maven/Java explorer preferences).

## Philosophy

- Keep global settings mostly language-agnostic.
- Put Java-specific project/runtime config in the workspace file.
- Optimize for keyboard-driven code exploration and refactoring.

## Quick start

1. Copy `profile/settings.json` and `profile/keybindings.json` into your VS Code user profile.
2. Copy `profile/java.code-workspace`, rename it for your project, and replace all `"..."` placeholders:
   - workspace folders
   - JDK runtime paths
3. Open the workspace file in VS Code.

## Expected extensions

For full keybinding behavior, install Java support extensions (at least language support + project tooling), since several keybindings call Java commands.

## Keybinding map (high level)

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

This setup is intentionally opinionated. Treat it as a base and adjust bindings/settings to your project and OS conventions.
