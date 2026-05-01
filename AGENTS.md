# Agent Context — alex-no-animal-violence

This repo distributes alex/retext-equality rule files for detecting speciesist language and industry euphemisms in text.

## Files

| File | Description |
|---|---|
| `animal-violence.yml` | Auto-generated alex/retext-equality rules for idioms that invoke animal harm (e.g. "kill two birds," "beat a dead horse"). Each rule provides `inconsiderate` terms, `considerate` alternatives, and a `note` with rationale. |
| `industry-euphemisms.yml` | Auto-generated rules for industry framing that obscures animal exploitation (e.g. "livestock," "poultry"). Same structure as `animal-violence.yml`. |
| `README.md` | Usage instructions for copying the YAML files into an alex or retext-equality config. |
| `.mcp.json` | MCP server config for this repo (local tooling, not committed upstream). |
| `AGENTS.md` | This file. |
| `LICENSE` | MIT license. |

## Toolchain position

This repo is a **generated distribution target** in the [Open Paws no-animal-violence](https://github.com/Open-Paws/no-animal-violence) suite. The canonical rule source lives in `no-animal-violence`; `tools/generate_all.py` in that repo writes both YAML files here. Do not edit the YAML files directly — raise changes in the canonical repo and re-run the generator.

Downstream consumers copy one or both YAML files into their [alex](https://github.com/get-alex/alex) or [retext-equality](https://github.com/retextjs/retext-equality) configuration.

## Constraints for agents

- **Do not edit `animal-violence.yml` or `industry-euphemisms.yml` manually.** Both are auto-generated; manual edits will be overwritten on the next generator run.
- **Do not add rule logic here.** New patterns belong in `no-animal-violence/rules.yaml`, not in this repo.
- Changes to `README.md`, `AGENTS.md`, or `LICENSE` follow the normal pipeline (branch → PR → merge).
- The only legitimate commit types here are: `chore:` (tooling/meta), `docs:` (README/AGENTS), or a regeneration commit from the generator (`chore: regenerate from no-animal-violence@<sha>`).
