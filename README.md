# Tecman Tools — Claude Code marketplace

A Claude Code plugin marketplace hosting Tecman developer tools.

## Plugins

| Plugin | Description |
|--------|-------------|
| `tecman-docx` | Generate or restyle Microsoft Word (`.docx`) documents in the Tecman house style and brand. Bundles the master logo and a `python-docx` generator library. |

## Install (any machine)

In Claude Code:

```
/plugin marketplace add <your-github-username>/<this-repo>
/plugin install tecman-docx@tecman-tools
```

Or from a terminal:

```bash
claude plugin marketplace add <your-github-username>/<this-repo>
claude plugin install tecman-docx@tecman-tools
```

> The `@tecman-tools` suffix is the **marketplace name** (from `marketplace.json`), not the repository name.

Requirements for the `tecman-docx` plugin: Python 3 with `python-docx` (`pip install python-docx`); optional Graphviz (`dot`) for diagrams.

## Update

After pushing changes (and bumping `version` in `plugin.json`), users refresh with:

```
/plugin marketplace update tecman-tools
```

## Validate before pushing

```bash
claude plugin validate .
```

## Layout

```
.claude-plugin/marketplace.json          # marketplace catalogue
plugins/tecman-docx/
  .claude-plugin/plugin.json             # plugin manifest
  skills/tecman-docx/
    SKILL.md                             # skill instructions + house-style spec
    assets/tecman_logo.png               # master logo
    scripts/tecman_docx.py               # python-docx generator
```
