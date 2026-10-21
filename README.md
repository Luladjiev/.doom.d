# Doom Emacs Configuration

Personal Doom Emacs configuration maintained in `~/.config/doom`.

## Appearance

- Catppuccin Latte in system light mode and Mocha in dark mode.
- System appearance is checked at startup and every five seconds of editor idle time. If detection is unavailable or fails, Windows uses Mocha and other systems use Latte.
- GUI editor font size of 14 pixels.
- Absolute line numbers, Doom dashboard and modeline, TODO highlighting, and version-control indicators in the fringe.

## Editing and Navigation

- Evil editing with Corfu completion, Orderless matching, and Vertico selection.
- Workspaces, Treemacs project drawer, Dired, and remote file access through TRAMP.
- File templates, snippets, folding, automatic formatting on save, indentation guessing, and whitespace trimming.
- Syntax checking, persistent undo, automatic delimiter pairing, and Doom's default keybindings.
- Magit, code and documentation lookup, and evaluation overlays.
- Eglot for LSP support and Tree-sitter for syntax parsing.

## Languages

Enabled language modules include Emacs Lisp, JavaScript/TypeScript, JSON, Markdown, Org, Python, shell, web, YAML, and Zig.

JavaScript and Zig enable both Tree-sitter and LSP support. Python enables LSP support as well.

## Terminal and Platform Integration

- Ghostel terminal with the `+everywhere` flag, available through `M-x ghostel`.
- macOS integration enabled on macOS.
- On Windows, Ghostel uses `pwsh.exe`. Other Emacs shell commands use Bash when it is available.
- On Windows, when `diff` is missing, the configuration adds Git for Windows' `usr/bin` directory to Emacs's executable search path and `PATH` if it contains `diff.exe`.

## Org and Mermaid

Org files live in `~/org/`. The agenda includes `.org` files recursively from that directory. `SPC n r` refreshes the agenda file list and redraws the current agenda buffer when invoked there.

Mermaid source blocks export to Markdown as fenced code blocks tagged `mermaid`:

```org
#+begin_src mermaid
flowchart LR
    A[Write Org] --> B[Export Markdown]
    B --> C[Render diagram]
#+end_src
```

Markdown export is available through `C-c C-e m m` or `M-x org-md-export-to-markdown`. Viewers with Mermaid support can render the exported diagrams.

Mermaid blocks default to `:exports code :eval never-export`, preserving diagram source without executing it during export. Other source blocks retain their usual Markdown export behavior.

## Configuration Files

| File | Contents |
| --- | --- |
| [init.el](init.el) | Enabled Doom modules and flags. |
| [packages.el](packages.el) | Additional package declaration for `catppuccin-theme`. |
| [config.el](config.el) | Appearance, editor preferences, platform integration, Org agenda, and Mermaid export settings. |
| [AGENTS.md](AGENTS.md) | Repository guidelines for contributors. |
