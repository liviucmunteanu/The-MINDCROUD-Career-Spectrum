# The MINDCROUD Career Spectrum

A complete, professional, commercially usable psychometric career assessment based on **Holland's RIASEC model** of vocational personality. The instrument helps adults (16+) identify their 2–3 dominant **Career Avatars** — the psychological career profiles where they have the highest probability of building a fulfilling and rewarding career.

> **Status:** Version 1.1 — English master version. **Not yet empirically validated**; see Section 10 (Validation Roadmap) of the master document before commercial use.
>
> v1.1 implements the critical fixes from a full simulated psychometric audit (8-stage / 120-persona protocol): 17 revised items, a deterministic gated classification algorithm, an expanded validity battery, and an accessible response UI. See [`validation/mindcroud-career-spectrum-psychometric-audit.md`](validation/mindcroud-career-spectrum-psychometric-audit.md) (evidence in [`validation/evidence/`](validation/evidence/)) and the Changelog at the end of the master document.

## The six Career Avatars

| Avatar | RIASEC dimension |
|---|---|
| The Maker | Realistic |
| The Explorer | Investigative |
| The Visionary | Artistic |
| The Mentor | Social |
| The Pioneer | Enterprising |
| The Guardian | Conventional |

Respondents receive a **Spectrum Heatmap** — a 0–100 Spectrum Score on all six Avatars — with the top 2–3 designated as Dominant Avatars, plus combination-based career recommendations aligned with O*NET job families.

## Repository contents

| Path | What it is |
|---|---|
| [`MINDCROUD-Career-Spectrum.md`](MINDCROUD-Career-Spectrum.md) | **The master document** — all 11 sections: overview, test blueprint, administration instructions, the 65-item form, item map, full scoring key, heatmap specification with 30 band narratives, the Career Recommendations Engine (all 15 two-Avatar combinations), psychometric specifications, validation roadmap, and ethical use guidelines. |
| [`data/items.json`](data/items.json) | Machine-readable item bank: all 65 administered items with position, internal code, Avatar, facet, keying, and quality-item metadata. |
| [`data/scoring.json`](data/scoring.json) | Machine-readable scoring key: reverse-scored items, scale rosters, Spectrum Score formula, Dominant Avatar rule, Differentiation Index, score bands, validity rules, and the 15 combination mappings. |
| [`tools/spectrum-scoring-tool.html`](tools/spectrum-scoring-tool.html) | **Self-contained interactive scoring tool** (no dependencies — open in any browser): administer the 65 items, then see the Spectrum Heatmap, Dominant Avatars, validity verdict, band narratives, and combination-based career recommendations. Includes demo-fill buttons for testing. |
| [`validation/`](validation/) | The full psychometric audit report and the evidence files behind it (5 expert-stage analyses, 120 persona definitions, 12 batch simulation results). |
| [`.claude/agents/spectrum-interpreter.md`](.claude/agents/spectrum-interpreter.md) | **Dedicated interpretation agent** for Claude Code: give it raw responses or Spectrum Scores and it validates the protocol, applies the v1.1 algorithm, and produces a consultant briefing and/or client-ready narrative report. |

## Instrument at a glance

- **60 scored items** (10 per Avatar scale, 3 facets each: activities, environments, energy/drain)
- **5 quality items**: 3 attention checks (at the 25/50/75% marks) + 2 consistency-check pairs
- **5-point Likert** agreement scale; 75% positively / 25% negatively keyed (antonym-based reversal)
- **Scoring:** raw 10–50 per scale → Spectrum Score 0–100 → ranked heatmap → 2–3 Dominant Avatars → Differentiation Index and validity flags
- **Target reliability:** Cronbach's alpha ≥ .80 per scale (benchmarked against the O*NET Interest Profiler Short Form, which shares the same 60-item/10-per-scale architecture)
- **Reading level:** 8th grade or below; idiom-free and designed for translation (ITC guidelines)

## Intended use

Career guidance, coaching, and self-directed exploration (medium stakes, development context). **Not** designed or validated for hiring, selection, promotion, or admission decisions — see the Ethical Use Guidelines (Section 11).

---

*The MINDCROUD Career Spectrum™ — © MINDCROUD. All items, scales, narratives, and scoring rules are original proprietary content. The Item Map and Scoring Key are confidential test material and must not be shown to respondents.*
