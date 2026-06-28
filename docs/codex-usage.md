# Codex Skill Management

Codex reads skills from several locations:

- Project skills: `.agents/skills`
- User skills: `~/.agents/skills`
- Admin skills: `/etc/codex/skills`
- System skills: bundled with Codex

This repository is the source of truth. Projects should symlink from this
repository instead of copying skill folders.

## Recommended Flow

Keep reusable skill source here:

```text
~/GitHub/skills/skills/<skill-name>
```

Link a skill into a project:

```bash
cd /path/to/project
mkdir -p .agents/skills
ln -s ~/GitHub/skills/skills/<skill-name> .agents/skills/<skill-name>
```

Remove a project link:

```bash
rm .agents/skills/<skill-name>
```

This removes only the symlink. The original skill remains in
`~/GitHub/skills`.

## Notes

Codex supports symlinked skill folders. When the source skill is updated in this
repository, every linked project sees the update automatically.

Claude Code may use `.claude/skills`, but Codex directly recognizes
`.agents/skills`, so no `.claude/skills` bridge is needed for Codex-only use.

