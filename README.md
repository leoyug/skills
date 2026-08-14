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

Example:

```bash
ln -s ~/GitHub/skills/skills/baoyu-design .agents/skills/baoyu-design
```

For skills with dependencies, link the dependency skills too:

```bash
ln -s ~/GitHub/skills/skills/grill-with-docs .agents/skills/grill-with-docs
ln -s ~/GitHub/skills/skills/grilling .agents/skills/grilling
ln -s ~/GitHub/skills/skills/domain-modeling .agents/skills/domain-modeling
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

## Collected Skills

| Skill | Source | Notes |
| --- | --- | --- |
| `baoyu-design` | https://github.com/JimLiu/baoyu-design/tree/main/skills/baoyu-design | Local design artifact generator for UI mockups, prototypes, decks, wireframes, design systems, and related HTML deliverables. |
| `grill-with-docs` | https://github.com/mattpocock/skills/tree/main/skills/engineering/grill-with-docs | Stateful grilling session for sharpening plans while maintaining glossary and ADR documentation. Depends on `grilling` and `domain-modeling`. |
| `grilling` | https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling | Reusable interview loop for stress-testing a plan, decision, or idea through rounds of frontier questions. |
| `domain-modeling` | https://github.com/mattpocock/skills/tree/main/skills/engineering/domain-modeling | Maintains project domain language in `CONTEXT.md` and records meaningful architecture decisions as ADRs. |
| `web-shader-extractor` | https://github.com/lixiaolin94/skills/tree/main/web-shader-extractor | Extracts, reproduces, and projectizes WebGL, WebGPU, Canvas, shader-like, animated, or interactive web visual effects. |
| `ian-xiaohei-scenes` | https://github.com/helloianneo/ian-xiaohei-scenes/tree/main/ian-xiaohei-scenes | Generates Chinese Xiaohei 2.0 real-object scene illustrations and long-scroll story images for articles, project retrospectives, and personal narratives. |
