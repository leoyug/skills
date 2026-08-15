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
| `ian-xiaohei-illustrations` | https://github.com/helloianneo/ian-xiaohei-illustrations/tree/main/ian-xiaohei-illustrations | Generates Ian-style Chinese Xiaohei hand-drawn article illustrations for methods, workflows, structures, metaphors, and conceptual explanations. |
| `character-design` | https://github.com/khanhhuyenngo985-sys/character-scene-design-skills/tree/main/skills/character-design | Designs production-ready character assets, proportion locks, turnarounds, wardrobe states, prop anchors, and AI image/video prompt packets. |
| `scene-design` | https://github.com/khanhhuyenngo985-sys/character-scene-design-skills/tree/main/.agents/skills/scene-design | Designs reusable scene systems, layouts, actor zones, power-space mechanisms, state ladders, and AI video scene continuity anchors. |
| `impeccable` | https://github.com/pbakaus/impeccable/tree/main/.agents/skills/impeccable | Frontend design director skill with commands for shaping, auditing, polishing, animating, colorizing, hardening, and live UI iteration. |
| `gsap-core` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-core | Official GSAP core API guidance for tweens, eases, durations, staggers, matchMedia, and basic DOM/SVG animation. |
| `gsap-timeline` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-timeline | Official GSAP timeline guidance for sequencing, nesting, playback control, and coordinated animation choreography. |
| `gsap-scrolltrigger` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-scrolltrigger | Official GSAP ScrollTrigger guidance for scroll-driven animation, pinning, scrub, parallax, and trigger setup. |
| `gsap-react` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-react | Official GSAP React and Next.js guidance for `useGSAP`, refs, context, cleanup, and component lifecycle safety. |
| `gsap-frameworks` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-frameworks | Official GSAP guidance for Vue, Nuxt, Svelte, SvelteKit, and other lifecycle-based frameworks. |
| `gsap-plugins` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-plugins | Official GSAP plugin guidance for registration and plugins such as Flip, Draggable, SplitText, MorphSVG, MotionPath, and more. |
| `gsap-performance` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-performance | Official GSAP performance guidance for smooth animation, transforms, opacity, batching, and avoiding layout thrashing. |
| `gsap-utils` | https://github.com/greensock/gsap-skills/tree/main/skills/gsap-utils | Official GSAP utilities guidance for clamp, mapRange, normalize, interpolate, random, snap, toArray, wrap, and pipe. |
| `transitions-dev` | https://github.com/Jakubantalik/transitions.dev/tree/main/skills/transitions-dev | CSS transition snippets and motion patterns for app UI micro-interactions such as modals, dropdowns, tooltips, accordions, toasts, and toggles. |
| `transitions-polish` | https://github.com/Jakubantalik/transitions.dev/tree/main/skills/transitions-polish | Motion polishing skill for tuning duration, distance, scale, blur, easing, stagger, and token alignment in existing transitions. |
