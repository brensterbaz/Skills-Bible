---
name: visual-direction-to-production-prompts
description: Turn an approved visual-direction brief into a production-ready prompt pack for a named image or video generation workflow. Use after the story and visual direction are approved and before any media is generated. Do not use to invent a visual style, rewrite the story, generate assets, animate, edit, add audio, render, or claim that prompted media exists.
---

# Visual Direction to Production Prompts

Translate approved creative decisions into prompts that a production tool or operator can run without losing the story, the visual system, or the guardrails.

This skill writes the **production prompt pack**. It does not generate the frames or film.

## Confirm the hand-off

Collect:

- the approved visual-direction brief and ordered scene list;
- the target image or video model, version, and supported controls;
- output format, aspect ratio, resolution, duration, and frame rate;
- supplied reference assets and permission to use them;
- caption, logo, product-interface, and safe-area requirements;
- any fixed seed, reference strength, camera, motion, or negative-prompt controls.

If the target model is not named, produce a **tool-neutral master pack** and clearly list the adapter decisions still required. Never invent model syntax or parameters.

## Lock what is approved

Extract a continuity sheet before writing scene prompts:

- recurring subject, objects, environment, materials, and textures;
- colour and typography roles;
- camera and lighting character;
- motion language and pacing;
- recurring graphic devices;
- claim, accessibility, and brand boundaries;
- details that must remain consistent across scenes.

Treat these as constraints, not inspiration. Do not introduce a new aesthetic because it sounds impressive in a prompt.

## Write one production unit per scene

For each scene, provide:

1. **Scene job** — the narrative purpose in one sentence;
2. **Master prompt** — subject, action, environment, composition, camera, light, material, colour, and mood in production order;
3. **Motion and timing** — only for moving output; describe the start, purposeful change, end state, and camera behaviour;
4. **Continuity locks** — the exact details that must match adjacent scenes;
5. **Overlay and safe-area note** — what should be added later rather than baked into generated media;
6. **Exclusions** — scene-specific mistakes, invented claims, and generic visual shortcuts to avoid;
7. **Parameters** — only controls supported by the named target model.

Use concrete nouns and observable actions. Prefer “a scuffed black phone judders three times on a navy workbench” to mood-only language such as “dynamic, cinematic, innovative”.

## Separate content from controls

Keep three layers distinct:

- **master prompt:** human-readable creative instruction;
- **negative or exclusion list:** what must not appear;
- **tool adapter:** verified syntax and supported parameters for the selected model.

Do not smuggle unsupported syntax into prose. Do not promise that identical seeds, camera phrases, or negative prompts behave the same across models.

## Protect the story and the evidence

- Preserve the approved scene purpose and voiceover meaning.
- Do not invent customer messages, product behaviour, logos, testimonials, interface screens, or performance results.
- Mark placeholders and supplied assets explicitly.
- Keep generated typography out of the frame when readable text will be added in edit.
- Reserve caption and interface safe areas in composition.
- Pair colour with labels, shape, position, or motion where meaning depends on a state change.
- Distinguish an instruction from a generated, reviewed, or approved result.

## Check the sequence

Before delivering, confirm that:

- every scene has one clear focal action;
- continuity locks recur without making every composition identical;
- camera, light, texture, and motion match the approved direction;
- the prompt does not contradict captions or voiceover;
- exclusions catch the most tempting generic or misleading result;
- safe areas are usable at the target aspect ratio;
- open model decisions are named rather than guessed;
- nothing implies that media has already been generated or approved.

## Deliver

Return:

1. **Target and assumptions**;
2. **Continuity sheet**;
3. **Ordered production prompt pack**;
4. **Global exclusions**;
5. **Tool-adapter decisions** still required, if any;
6. **Production checklist** for the operator who will run the prompts.

Stop after the prompt pack. Do not generate images or video, source assets, animate, edit, add audio, render, publish, or describe unmade output as finished.
