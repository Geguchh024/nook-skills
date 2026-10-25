# Nook skills

[Claude Code](https://claude.com/claude-code) skills for
[Nook](https://github.com/Geguchh024/nook), the floating notch for Windows.

| Skill | What it does |
|---|---|
| [nook-plugin](nook-plugin) | Builds, fixes, tests and publishes Nook plugins (tiles). Knows the exact `plugin.toml` rules, every message and component, the icon names, and the mistakes that leave a tile blank. Bundles a checker that runs your plugin the way Nook does and reports anything Nook would skip. |

## Install

Clone this repository and copy the skill into your personal skills folder, so
Claude Code can use it in every project:

```powershell
git clone https://github.com/Geguchh024/nook-skills.git
Copy-Item -Recurse nook-skills\nook-plugin "$HOME\.claude\skills\" -Force
```

Or put it in your plugin's repository at `.claude\skills\nook-plugin\` and
commit it, so everyone who works on the plugin gets it.

Restart Claude Code (or start a new session) to pick it up.

## Use it

Describe the tile you want. Claude Code uses the skill on its own when you
talk about a Nook plugin, a tile for the notch or `plugin.toml`, and you can
also call it by name with `/nook-plugin`.

Run the checker yourself after any change:

```powershell
python "$HOME\.claude\skills\nook-plugin\scripts\check_plugin.py" C:\code\my-plugins\weather --event refresh:click
```

The skill is plain Markdown and a Python script. Read it before you install
it, like any code you run.

## Where it comes from

This repository mirrors `skills/` in the Nook repository, where the skill is
developed. Changes to the protocol land there first; `python skills/pack.py`
in a Nook checkout refreshes the copied SDK files and icon list.

## License

MIT
