# Paper Ops

A skill bundle for academic writing, manuscript management, and reviewer responses.

**v0.1.0 · MIT License**

Repository: [xy727682/paper-ops](https://github.com/xy727682/paper-ops)

[简体中文](README.zh-CN.md) · [External skills](EXTERNAL_SKILLS.md) · [Attribution](ATTRIBUTION.md) · [Release notes](RELEASE_NOTES.md)

## Included skills

- [**paper-ops**](skills/paper-ops/SKILL.md) manages manuscript versions, experimental data provenance, figure consistency, rendering, and delivery.
- [**academy-writing**](skills/academy-writing/SKILL.md), developed by the project team, guides literature-informed drafting, terminology management, and evidence-aligned revisions.
- [**seven-step-rebuttal**](skills/seven-step-rebuttal/SKILL.md), developed by the project team, connects review comments, response arguments, author edits, and manuscript revisions.

All three are SKILL.md workflows for a compatible agent, rather than standalone software. They can be used independently or together.

## Installation

Download [v0.1.0](https://github.com/xy727682/paper-ops/releases/tag/v0.1.0) or clone the repository:

```bash
git clone https://github.com/xy727682/paper-ops.git
```

Copy the complete directories `skills/paper-ops/`, `skills/academy-writing/`, and `skills/seven-step-rebuttal/` into the skill location supported by your agent. Keep the supporting files, not just SKILL.md.

- Compare or back up existing skills before replacing a directory with the same name.
- Follow your client's instructions for skill discovery and loading. Cross-client compatibility has not been tested for this release.
- The optional external skill is not required to use the three bundled workflows.

Document extraction and compilation use tools available in the host environment. No compiler, OCR engine, paper corpus, or automatic scoring system is bundled.

## Optional external skills

[ml-paper-humanizer by Fwibo](https://github.com/Fwibo/ml-paper-humanizer) is an optional external writing integration. Its instructions, scripts, and corpora are not distributed here. It is not required for the included workflows. `academy-writing` is developed by the project team and included in this bundle. See [EXTERNAL_SKILLS.md](EXTERNAL_SKILLS.md) for the upstream link.

## Example requests

> Use paper-ops to update Section 4.2 from the supplied CSV. Work from the specified main.tex, preserve other sections, and create a separate working copy. Do not run experiments.

> Use seven-step-rebuttal to map the annotated PDF comments to the manuscript. Preserve the original comments, draft responses supported by the supplied evidence, and return a response map and marked manuscript.

For a local edit, limit the workflow to that edit. A caption change does not require a full manuscript review. Missing evidence stays explicit in working drafts; it is never replaced by invented results.

## Core contributors

- [dodn-2021](https://github.com/dodn-2021) — Co-developer
- [xy727682](https://github.com/xy727682) — Co-developer

## License

This bundle uses the [MIT License](LICENSE). See [ATTRIBUTION.md](ATTRIBUTION.md) for attribution. The optional external project is linked separately and not bundled or represented as a co-author.
