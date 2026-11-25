# distinct-ui

An agent skill that stops your AI coding agent from shipping the same generated-looking UI every time: it plans a design from the subject, checks the plan for template defaults, then builds and critiques.

Works with Claude Code and any agent harness that loads `SKILL.md` skills.

## Why

Ask an agent for a landing page and you get the same look every time: cream background with a terracotta accent, or near-black with acid green, identical rounded cards, ALL-CAPS eyebrows, `01 / 02 / 03` markers, and a fade-up on every section. None of these is wrong on its own. They're defaults, though, not choices. This skill makes the agent:

- start from the product, the audience, and the page's job
- commit to a small token plan (color, type, layout, one signature element) before writing code
- test that plan against a checklist of common "AI look" tells and revise it
- meet an accessibility and responsiveness floor without being told
- write interface copy that is plain, specific, and consistent

## How it works

```
  brief arrives ("build a landing page for …")
          │
          ▼
  1. Pin the subject ────── product, audience, one job (propose if missing)
          │
          ▼
  2. Design plan ─────────── 4–6 hex colors · 1–2 typefaces · ASCII wireframe · signature
          │
          ▼
  3. Check vs. brief ─────── "would I make this for any similar prompt?" → revise
          │
          ▼
  4. Build
          │
          ▼
  5. Critique ────────────── screenshot · remove one accessory · quality floor
```

| Default the agent reaches for | What the skill pushes toward |
|---|---|
| Cream + serif + terracotta, or black + acid green | A palette taken from the subject's world |
| Identical rounded cards with soft grey shadows | Containers that vary by hierarchy |
| ALL-CAPS eyebrow over every heading | Headings that stand alone |
| `01 / 02 / 03` markers | Numbers only for real sequences |
| Fade-up on every section | One orchestrated moment |
| "Submit" | "Save changes" |

If the brief asks for one of these looks, the agent follows the brief.

## Install

**Claude Code (personal, all projects):**

```bash
git clone https://github.com/RK905/distinct-ui /tmp/dui
cp -r /tmp/dui/skills/distinct-ui ~/.claude/skills/
```

**One project only:** copy `skills/distinct-ui` into `<project>/.claude/skills/`.

**Other harnesses:** point your agent at `skills/distinct-ui/SKILL.md` (Codex, Cursor, Gemini CLI, and others can load it as an instruction file or rule).

## Usage

The skill triggers on its own when the agent builds or restyles UI. You can also call it directly:

```
/distinct-ui landing page for a small-batch hot sauce brand, React + Tailwind
```

| Input | What it is | Example |
|---|---|---|
| `brief` | What to build and for whom | `landing page for a hot sauce brand` |
| `constraints` | Stack, brand colors, fonts, must-haves (optional) | `Tailwind`, `brand red #C8102E` |
| `existing UI` | Files or screenshots to restyle (optional) | `src/pages/index.tsx` |

**Example plan (step 2):**

```
Color:  Habanero #E4572E · Smoke #2B2118 · Jar-glass #F2EDE4 · Label-gold #E8B04B · Leaf #4F6D3A
Type:   Display: a condensed grotesk, set huge · Body: a humanist sans
Layout: Full-bleed bottle photo, heat scale running down the left edge as navigation
        ┌───────────────┬──────┐
        │  BOTTLE IMG    │ heat │
        │  headline      │ 1–5  │
        └───────────────┴──────┘
Signature: the Scoville heat scale as the page's spine
Revised: dropped the cream background (generic default) for jar-glass off-white with smoke text.
```

## Tips

- Put brand colors and fonts in the brief. The skill treats the brief as binding.
- If your harness can take screenshots (Playwright, a browser tool), let the agent use them in step 5.
- Keep a `design-notes.md` in the project so later passes try something new.

## Credits

Based on the `frontend-design` skill from [anthropics/skills](https://github.com/anthropics/skills) by Anthropic, licensed under Apache-2.0. See [NOTICE](NOTICE) for what changed.

## License

Apache-2.0. See [LICENSE](LICENSE).
