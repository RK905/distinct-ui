---
name: distinct-ui
description: Use when building a new UI or restyling an existing one (pages, landing sites, dashboards, components) and the result should look designed for this subject, not like a generated template. Gives a plan → check → build → critique loop plus a list of default "AI look" tells to avoid.
---

# Distinct UI

Design like a studio whose client already rejected two templated proposals. Every visual choice should come from **this** brief's subject, not from habit.

## The loop

1. **Pin the subject.** Name the product, the audience, and the page's one job. If the brief doesn't say, propose all three and confirm. Pull ideas from the subject's world: its materials, vocabulary, artifacts. Use real content, not lorem ipsum.
2. **Write a tiny design plan** before any code:
   - **Color:** 4–6 named hex values.
   - **Type:** 1–2 families (clearly different if 2) and a type scale.
   - **Layout:** one sentence + an ASCII wireframe; say how content aligns.
   - **Signature:** the *one* bold element this page will be remembered for.
3. **Check the plan against the brief.** Ask: "Would I produce this for any similar prompt?" Any part that's a default, not a choice, gets revised. Note what changed and why.
4. **Build** from the revised plan.
5. **Critique.** Screenshot it if you can. Remove one accessory. Confirm the quality floor (below).

The brief always wins. If it asks for a look on the tells list, do exactly that.

## Defaults to avoid (unless the brief asks)

| Tell | Instead |
|---|---|
| Cream bg (~#F4F1EA) + serif display + terracotta accent (~#D97757) | Palette taken from the subject |
| Near-black bg + one acid-green/vermilion accent | Same |
| Broadsheet: hairline rules, 0 radius, dense columns | Layout that fits the content's shape |
| Identical rounded cards, one radius, soft grey shadow, gradient washes | Vary containers by hierarchy; drop decoration |
| ALL-CAPS tracked eyebrow over every heading | Let the heading stand alone |
| `A · B · C` meta strings, `WORD — fragment` labels, `→` on every link | Plain labels |
| #0B0B0B/#111 as "black", mono font for tiny labels | Deliberate neutrals and type |
| Hero = big number + small label + stats + gradient | The most characteristic thing in the subject's world (image, demo, headline, interaction) |
| One word in a headline italic/bold/colored | Let type treatment carry the whole line |
| 01 / 02 / 03 markers | Only for real sequences (steps, timelines) |
| Fade-slide-up on every section, hover motion on every card | One orchestrated moment; motion that answers user actions is fine |

## Type and structure

- Line length under ~80 characters; serif body gets a bit more line-height.
- Pick typefaces on purpose, not your usual pair. Headline type is part of the design, not just a container for words.
- Borders, numbers, labels, and dividers carry information. If one doesn't, cut it.

## Quality floor (don't announce it, just meet it)

Responsive to mobile · visible keyboard focus · `prefers-reduced-motion` respected · accessible contrast · coherent palette · no CSS selectors that override each other (watch section padding/margin).

## Copy

Words are design content. Each one does a single job.

- Name things the way users think of them ("Notifications", not "Webhook config"). Describe, don't sell.
- Active voice, sentence case, plain verbs. Buttons say what happens: "Save changes", not "Submit".
- Keep an action's name the same everywhere: "Publish" → "Published".
- Errors say what happened and how to fix it, without apologizing. Empty states invite the next action.

## Memory

If you can keep notes, write down what you tried on this project so the next pass explores something new.
