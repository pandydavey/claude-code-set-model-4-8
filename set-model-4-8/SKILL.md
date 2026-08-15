---
name: set-model-4-8
description: Switch the default Claude Code model to Opus 4.8 or Sonnet 4.8 by pinning the id in settings.json. Use when the user says "switch to opus 4.8", "use sonnet 4.8", "set model to ...", or is unhappy with Opus 5 / Sonnet 5.
disable-model-invocation: true
---
# set-model

Pin the default model in `~/.claude/settings.json` (the `/model` picker can't list 4.8 ids).

Model ids:
- Opus 4.8 - `claude-opus-4-8`
- Sonnet 4.8 - `claude-sonnet-4-8`

Edit the `"model"` key in `~/.claude/settings.json` to the requested id. Then tell the user:

> Set default to `<id>` in settings.json. Applies to new sessions; for this session run `/model <id>` or restart. Don't re-pick via `/model` afterward — that overwrites this key.