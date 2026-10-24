# visual-direction-to-production-prompts

Turn an approved visual-direction brief into a continuity sheet and one production prompt per scene.

## What it does

- Preserves the approved visual decisions.
- Separates sequence-wide continuity from scene-specific instructions.
- Writes model-aware prompts when a target tool is known.
- Returns a tool-neutral master pack when the target model is still undecided.

## Boundary

It writes prompts. It does not generate images or video, source assets, animate, edit, add audio, render or publish.

## Install

```bash
npx skills@latest add brensterbaz/Skills-Bible --skill=visual-direction-to-production-prompts
```

## Example request

> Translate this approved visual direction into a continuity sheet and six prompts for the named image model. Preserve the safe areas and negative constraints.

## Safety

The skill is instruction-only and contains no executable scripts. Review [`SKILL.md`](SKILL.md) and your agent’s permissions before use.
