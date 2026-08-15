# claude-code-set-model-4-8

Currently you cant set claude code to 4.8 without knowing the key.

A tiny [Claude Code](https://claude.com/claude-code) skill to pin your default model to **Opus 4.8** or **Sonnet 4.8**.

The `/model` picker only lists the model versions shipped with your Claude Code build, so newer/older ids like `claude-opus-4-8` may not appear. This skill just edits the `model` key in your `settings.json` for you.

## Install

Copy the skill into your Claude Code skills directory:

```bash
# Global (all projects)
mkdir -p ~/.claude/skills/set-model
curl -o ~/.claude/skills/set-model/SKILL.md \
  https://raw.githubusercontent.com/<you>/set-model/main/SKILL.md
```

Or drop SKILL.md under .claude/skills/set-model/ in a specific repo for a project-scoped install.

Usage

In Claude Code:

/set-model opus 4.8
/set-model sonnet 4.8

Or just ask: "switch to opus 4.8".

Model ids

┌────────────┬───────────────────┐
│   Model    │        id         │
├────────────┼───────────────────┤
│ Opus 4.8   │ claude-opus-4-8   │
├────────────┼───────────────────┤
│ Sonnet 4.8 │ claude-sonnet-4-8 │
└────────────┴───────────────────┘

Set it manually

The skill only edits one line — you can do it yourself in ~/.claude/settings.json:

{
  "model": "claude-opus-4-8"
}

Applies to new sessions. For the current session, run /model claude-opus-4-8 or restart.

▎ ⚠️ Don't re-pick a model via the /model picker afterward — it overwrites this key.

License

MIT
