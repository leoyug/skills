# Skills

Personal Codex skills repository for skills I create, adapt, or collect from
other sources.

## Structure

```text
skills/
  skill-name/
    SKILL.md
    scripts/
    references/
    assets/
docs/
  codex-usage.md
```

Each skill is a folder containing a `SKILL.md` file. Optional `scripts/`,
`references/`, and `assets/` folders live next to `SKILL.md` when the workflow
needs them.

## Use In A Codex Project

For project-level use, symlink only the skills needed by that project:

```bash
mkdir -p .agents/skills
ln -s ~/GitHub/skills/skills/example-skill .agents/skills/example-skill
```

Codex scans `.agents/skills` from the current working directory up to the
repository root. Keeping skills project-scoped reduces accidental triggers and
keeps the initial skills list focused.

## Use Globally

For personal skills that should be available in every Codex project:

```bash
mkdir -p ~/.agents/skills
ln -s ~/GitHub/skills/skills/example-skill ~/.agents/skills/example-skill
```

Use this sparingly. Global skills are convenient, but too many of them can make
skill discovery noisy.

## Add A New Skill

1. Copy `skills/_template` to `skills/<skill-name>`.
2. Edit `SKILL.md`.
3. Keep the `description` short and specific, because Codex uses it to decide
   when to load the skill.
4. Test with an explicit invocation like `$skill-name`.

