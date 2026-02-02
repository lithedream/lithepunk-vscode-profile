# Keymap - lithepunk Profile

This keymap is intentionally shaped by Eclipse muscle memory for lost souls moving to VS Code: fast symbol lookup, hierarchy-first navigation, and minimal mouse use.

## The mental model (memorable layout)

- `Alt+1..3` = "jump deck core" (`1` workspace symbols, `2` code outline/symbols, `3` quick open)
- `Alt+4/5` = secondary views (Explorer and Outline focus)
- `F3/F4` = "type drill-down" (definition and hierarchy)
- `Alt+A/Q` = "relationship lenses" (references and call hierarchy)
- `Alt+Left/Right` = "time travel" (back/forward nav history)
- `Ctrl+1` = "fix now" (quick fix, Eclipse-style)

## Active bindings

| Key | Command | When | Intent / Eclipse influence |
|---|---|---|---|
| `Alt+1` | `workbench.action.showAllSymbols` | always | Workspace symbols (close to "Open Type") |
| `Alt+2` | `java.action.showExtendedOutline` | `javaLSReady && editorLangId == 'java'` | Java structure view (Outline-like) |
| `Alt+2` | `workbench.action.gotoSymbol` | `!javaLSReady || editorLangId != 'java'` | Fallback symbol nav for non-Java |
| `Alt+3` | `workbench.action.quickOpen` | always | Quick file/resource open |
| `Alt+4` | `workbench.view.explorer` | `viewContainer.workbench.view.explorer.enabled` | Project explorer focus |
| `Alt+5` | `outline.focus` | always | Outline panel focus |
| `Alt+E` | `workbench.action.showAllEditors` | always | Open editors list |
| `F3` | `editor.action.revealDefinition` | `editorHasDefinitionProvider && editorTextFocus` | Go to definition (classic Eclipse habit) |
| `F4` | `java.action.showTypeHierarchy` | always | Java type hierarchy |
| `Alt+A` | `references-view.findReferences` | `editorHasReferenceProvider` | Find references |
| `Alt+Q` | `references-view.showCallHierarchy` | `editorHasCallHierarchyProvider` | Call hierarchy |
| `Alt+Left` | `workbench.action.navigateBack` | `canNavigateBack` | Navigate back |
| `Alt+Right` | `workbench.action.navigateForward` | `canNavigateForward` | Navigate forward |
| `Ctrl+1` | `editor.action.quickFix` | `editorHasCodeActionsProvider && textInputFocus && !editorReadonly` | Quick fix / assist |
| `Ctrl+L` | `workbench.action.gotoLine` | always | Go to line |
| `Ctrl+Shift+C` | `editor.action.commentLine` | `editorTextFocus && !editorReadonly` | Toggle line comment |
| `Ctrl+D` | `editor.action.deleteLines` | `textInputFocus && !editorReadonly` | Delete line |
| `Alt+Z` | `actions.find` | `editorFocus || editorIsOpen` | Find in editor |
| `Escape Escape` | `workbench.action.toggleZenMode` | `!isAuxiliaryWindowFocusedContext && editorFocus` | Fast distraction-free toggle |

## Removed default bindings (intentional conflict cleanup)

| Key | Removed command | When | Why removed |
|---|---|---|---|
| `Ctrl+1` | `workbench.action.focusFirstEditorGroup` | always | Free `Ctrl+1` for quick fix |
| `Alt+1` | `workbench.action.openEditorAtIndex1` | always | Free `Alt+1` for symbols |
| `Alt+2` | `workbench.action.openEditorAtIndex2` | always | Free `Alt+2` for outline/symbols |
| `Alt+3` | `workbench.action.openEditorAtIndex3` | always | Free `Alt+3` for quick open |
| `Alt+4` | `workbench.action.openEditorAtIndex4` | always | Free `Alt+4` for explorer |
| `Alt+5` | `workbench.action.openEditorAtIndex5` | always | Free `Alt+5` for outline |
| `F3` | `editor.action.nextMatchFindAction` | `editorFocus` | Keep `F3` dedicated to definition |
| `F3` | `list.find` | `listFocus && listSupportsFind` | Avoid collisions with definition flow |
| `F3` | `list.find.replInputFocus` | `view == 'workbench.panel.repl.view'` | Same reason |
| `F3` | `workbench.action.terminal.findNext` | terminal find contexts | Same reason |
| `F4` | `references-view.next` | references view contexts | Keep `F4` dedicated to type hierarchy |
| `F4` | `search.action.focusNextSearchResult` | search contexts | Same reason |
| `F4` | `goToNextReference` | reference search contexts | Same reason |
| `Ctrl+L` | `workbench.action.chat.newChat` | `chatIsEnabled && inChat && chatLocation == 'panel'` | Free `Ctrl+L` for go-to-line |
| `Ctrl+L` | `expandLineSelection` | `textInputFocus` | Same reason |
| `Ctrl+L` | `notebook.centerActiveCell` | `notebookEditorFocused` | Same reason |
| `Ctrl+Shift+C` | `workbench.action.terminal.openNativeConsole` | `!terminalFocus` | Free for editor commenting |
| `Alt+Z` | `editor.action.toggleWordWrap` | always | Free for find |
| `Alt+A` | `editor.action.accessibilityHelpConfigureAssignedKeybindings` | accessibility help contexts | Free for references |
| `Alt+Right` | `quickInput.acceptInBackground` | quick pick contexts | Preserve forward navigation |
| `Ctrl+D` | `editor.action.addSelectionToNextFindMatch` | `editorFocus` | Free for delete line |
| `Ctrl+M` | `editor.action.toggleTabFocusMode` | always | Prevent accidental toggle |

## Notes

- Several bindings call Java extension commands; without Java tooling installed, only generic fallback bindings apply.
- This is an intentionally opinionated map optimized for Java codebase navigation and refactoring speed.
