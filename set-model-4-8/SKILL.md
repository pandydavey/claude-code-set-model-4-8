---
name: set-model-4-8
description: Switch the default Claude Code model to a legacy Claude id by pinning it in settings.json. Use when the user says "switch to opus 4.8", "use sonnet 4.6", "set model to ...", or is unhappy with Opus 5 / Sonnet 5.
disable-model-invocation: true
---
# set-model

Pin the default model in `~/.claude/settings.json` (the `/model` picker can't list legacy ids).

Model ids (legacy, per https://platform.claude.com/docs/en/about-claude/models/overview — verify against that page before using, since ids are added/deprecated over time):
- Opus 4.8 → `claude-opus-4-8`
- Sonnet 4.6 → `claude-sonnet-4-6`
- Sonnet 4.5 → `claude-sonnet-4-5-20250929`
- Opus 4.5 → `claude-opus-4-5-20251101`

If the user names an id/version not in this list (or not on the docs page), do not guess or invent one — tell them it doesn't exist and ask which real id they meant.

Steps:
1. Fetch the models overview doc and confirm the requested id is listed (current or legacy table) before editing anything.
2. Read `~/.claude/settings.json`.
3. Edit only the value of the existing `"model"` key — never append a second `"model"` key. If the file has no `"model"` key, add exactly one.
4. After editing, re-read the file and confirm it parses as valid JSON (e.g. `jq . ~/.claude/settings.json`) before reporting success. If it doesn't parse, fix it before telling the user anything is done.

Then tell the user:

> Set default to `<id>` in settings.json. Applies to new sessions; for this session run `/model <id>` or restart. Don't re-pick via `/model` afterward — that overwrites this key.
