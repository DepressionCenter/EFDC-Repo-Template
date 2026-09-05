<!--
This file is part of YOUR_PROJECT_TITLE
Copyright © YOUR_YEAR The Regents of the University of Michigan
Licensed under the GNU Free Documentation License v1.3 or later.
See <https://www.gnu.org/licenses/fdl-1.3.html>. See README for full license information.
-->

# YOUR_PROJECT_TITLE

## Skills folder

[Back to project README](../README.md)

Keep reusable project workflows here, one folder per skill. No skills are included
yet; this folder contains this guide and the project-specific instruction stub.

### What belongs here

Each future skill lives at `skills/<skill-name>/SKILL.md`, with lowercase letters,
digits, and hyphens in the folder name. Start the file with YAML frontmatter
containing `name` (matching the folder) and `description` (what it does and when to
use it). Follow with a short Markdown workflow, relevant constraints, and ways to
verify the result. Put the required hidden license notice after the frontmatter
so the skill parser can read the metadata first.

Keep repository-specific facts and conventions in [PROJECT.md](PROJECT.md).
Add `references/`, `scripts/`, or `assets/` inside a skill only when needed. Link
supporting files from `SKILL.md`; keep project rules in `AGENTS.md` and list each
reviewed skill in [the root index](../SKILLS.md). Never store secrets, real research
data, generated caches, or unrelated manuals here.

### Claude Code and Codex

The shared `SKILL.md` format works with both tools. A top-level `skills/` folder
alone does not enable native skill discovery.

| Use | Location or entry point |
| --- | --- |
| Shared source | `skills/<skill-name>/SKILL.md` |
| Repository guidance | `AGENTS.md` points to `SKILLS.md` |
| Claude Code project instructions | Root `CLAUDE.md` imports `AGENTS.md` |
| Codex native discovery | `.agents/skills/<skill-name>/SKILL.md` |
| Claude Code native discovery | `.claude/skills/<skill-name>/SKILL.md` |

For now, the instruction-file route is sufficient. When adding real skills,
copy the complete reviewed skill folder into each tool's discovery directory, or
use a directory symlink per skill where supported. Keep `skills/` as the source
of truth: refresh copies together and compare them after edits. Symlinks avoid
copy drift but require suitable checkout support and permissions on Windows.

This template ignores `.claude/` local configuration. Local copies still work,
but shared native Claude skills need narrow `.gitignore` exceptions for their
folders and parent directories. Do not expose all local settings to Git. No
native skill folders, copies, or symlinks are installed by this template.

Use only shared frontmatter fields unless a tool-specific feature is necessary.
Avoid executable prompt interpolation, tool-specific variables, and automatic
hooks in portable skills. Verify discovery in both actual clients before claiming
native integration works.

### Review before adoption

Prefer official documentation for the project's actual runtime and version.
Review third-party instructions, scripts, dependencies, licenses, network access,
and side effects before installation. Popularity is not evidence of safety.
Adapt the [authoring examples](../docs/skill-examples.md) to real project commands;
do not copy every example into every project.

### Conclusion

Keep this folder small and task-focused. Add a skill when it captures useful
project knowledge, then update the root index and verify its behavior.

### Additional resources

- [Project instructions](../AGENTS.md)
- [Project-specific instructions](PROJECT.md)
- [Root skills index](../SKILLS.md)
- [Skill authoring examples](../docs/skill-examples.md)
- [Agent Skills specification](https://agentskills.io/specification)
- [Codex skills documentation](https://developers.openai.com/codex/skills/)
- [Claude Code skills documentation](https://code.claude.com/docs/en/skills)
- [Claude Code shared instruction import](https://code.claude.com/docs/en/memory#agentsmd)

[Back to project README](../README.md)
