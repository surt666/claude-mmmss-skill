# mmmss

A shareable Claude Code skill that teaches agents to work in **Many More Much Smaller Steps** — GeePaw Hill's way of changing software as a path of small steps that each go from ready to ready.

## What the skill teaches

- **Define "ready"** for the repo (tests/build/lint pass, nothing user-visible worse) and check it before starting.
- **Plan a path, not a destination** — a numbered list of ~15-minute steps, each ending ready; no-value preparatory steps are legal.
- **Check and commit every step** — stage only that step's files; one local commit per step, no push.
- **Revert, don't push on** — a step that won't go green quickly is restored and split.
- **Expand → migrate → contract** for restructures; refactor and behaviour change in separate steps.
- A red-flags table for the usual rationalisations ("create all files, then test", "the user said in one go").

The skill activates automatically when an agent is about to change code, content, config or infrastructure.

**Note:** the skill tells agents the user has authorised one local commit per step. Only install it where that's true.

## Install (team)

Point Claude Code at this repo as a marketplace, then install the plugin:

```
/plugin marketplace add surt666/claude-mmmss-skill
/plugin install mmmss@mmmss-marketplace
```

Or add it to a project's `.claude/settings.json` so everyone on the repo gets it automatically:

```json
{
  "extraKnownMarketplaces": {
    "mmmss-marketplace": {
      "source": { "source": "github", "repo": "surt666/claude-mmmss-skill" }
    }
  },
  "enabledPlugins": ["mmmss@mmmss-marketplace"]
}
```

## Layout

```
.claude-plugin/marketplace.json     # marketplace manifest (lists the plugin)
plugins/mmmss/
  .claude-plugin/plugin.json        # plugin manifest
  skills/mmmss/SKILL.md             # the skill itself
```

## Source

GeePaw Hill, *Many More Much Smaller Steps* (2021): https://www.geepawhill.org/series/many-more-much-smaller-steps/

## License

MIT — adapt freely.
