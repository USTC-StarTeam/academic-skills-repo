# Academic Skills Repo

Reusable skills for academic research workflows, paper-code releases, repository polishing, documentation, project pages, citation metadata, and reproducibility support.

The skills in this repository are written to be tool-agnostic where possible. They can be adapted for Codex, Claude, Cursor, other agentic coding tools, or custom research automation agents.

## Skills

| Skill | Purpose |
| --- | --- |
| [`polish-academic-repos`](skills/polish-academic-repos/SKILL.md) | Improve academic-paper code repositories with clearer README/docs, paper metadata, figures, experiment summaries, citation, contact, hosted pages, and release validation. |

## Suggested Layout

```text
skills/
  skill-name/
    SKILL.md
    agents/
      openai.yaml
```

Use one directory per skill. Keep each `SKILL.md` self-contained and place optional agent-specific metadata under `agents/`.

## Using A Skill

For Codex-style skill discovery, copy or sync a skill folder into the local skills directory used by your agent. For Claude, Cursor, or other tools, copy the `SKILL.md` content into the equivalent skill, rule, instruction, or workflow mechanism.

Each skill should remain portable:

- avoid hard-coding one hosting platform unless required
- prefer capability names over tool names
- include validation steps that work locally and remotely
- state manual handoff steps when automation is unavailable
