# Skills Bible — Brendan Tack’s AI skills

The canonical home for Brendan’s reusable agent skills. Each skill has a clear purpose, explicit boundaries and inspectable Markdown instructions.

## Skill catalogue

### Content planning and production hand-offs

| Skill | Input → output | Stops before |
| --- | --- | --- |
| [brief-to-script](skills/brief-to-script/) | Rough brief → spoken-word script | Storyboarding and production |
| [script-to-storyboard](skills/script-to-storyboard/) | Script → narrative scene map | Visual direction and artwork |
| [storyboard-to-visual-direction](skills/storyboard-to-visual-direction/) | Storyboard → visual-design brief | Model-specific prompts and generation |
| [visual-direction-to-production-prompts](skills/visual-direction-to-production-prompts/) | Visual direction → continuity sheet and prompt pack | Asset generation, editing and rendering |

The stages deliberately remain separate:

```text
brief → script → storyboard → visual direction → production prompts
```

### Website quality

| Skill | Purpose |
| --- | --- |
| [site-production-polish-audit](skills/site-production-polish-audit/SKILL.md) | Evidence-led audit of 20 production-quality checks: branding, metadata, states, accessibility, performance, mobile layouts and working controls. |

The audit is read-only by default. Findings require evidence or explicit limitations; remediation and deployment need separate authorization. Its related Hermes skills are optional companion workflows and are not bundled here.

## Install

Using the Skills CLI:

```bash
npx skills@latest add brensterbaz/Skills-Bible --skill=brief-to-script
```

Replace the skill name with any folder in the catalogue. Alternatively, review and copy the complete chosen skill folder into your agent’s supported skills directory. Invocation and tool availability depend on the agent client.

## Safety and permissions

These skills are instruction-only Markdown, not executable packages. They do not include scripts, binaries, install hooks or credentials. Agent permissions still matter: inspect instructions, constrain tool access and review externally consequential actions.

Read [SECURITY.md](SECURITY.md). File integrity checks are in [SHA256SUMS](SHA256SUMS); they verify bytes, not safety or successful task execution.

## Consolidation and provenance

The four content-production skills were imported from [brensterbaz/ai-skills](https://github.com/brensterbaz/ai-skills) at commit `e7dd7572b51a5ce8f1de5703f9fda0008db19263`. Their `SKILL.md` files are unchanged; their README installation commands now point here. The original repository retains its history and files as a read-only archive.

The website audit was already maintained here and is preserved unchanged. Future skill development belongs in this repository.

## Licence

[MIT](LICENSE). Original attribution is retained.
