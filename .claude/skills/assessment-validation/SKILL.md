---
name: assessment-validation
description: Conduct a PhD-level psychometric validation of any assessment instrument — career assessments, personality tests, leadership inventories, engagement surveys, 360-feedback tools, or any self-report measure. Use this skill whenever the user mentions validating an assessment, psychometric analysis, test validation, instrument review, assessment audit, scale development review, construct validity, item analysis, or wants to stress-test a questionnaire or survey with simulated personas. Also trigger when users say "validate my assessment", "review my test", "psychometric audit", "is my assessment any good", "test my instrument", "/assessment-validation", or upload a document containing survey items, Likert scales, scoring algorithms, or typology systems and ask for feedback. This skill runs a rigorous 8-stage analysis pipeline with 120 simulated persona tests executed via subagents in parallel, producing a formal .md audit report.
---

# Assessment Validation Skill

## What This Skill Does

Runs a comprehensive psychometric validation pipeline on any uploaded assessment instrument. The pipeline has 8 stages, uses subagents for parallel persona testing, and produces a formal `.md` audit report.

## Prerequisites

- The user must upload or provide the assessment instrument (PDF, DOCX, or pasted text)
- Claude Code environment with subagent capability
- The instrument should contain: items/questions, scoring methodology, and ideally a classification/typology system

## Workflow Overview

```
Stage 1: Construct & Content Validity Analysis
Stage 2: Item-Level Quality Analysis
Stage 3: Dimensional Structure & Classification Validity
Stage 4: Comparative Analysis vs. Established Instruments
Stage 5: Bias, Fairness & Cross-Cultural Analysis
Stage 6: Persona Generation (120 custom personas tailored to this instrument)
Stage 7: Persona Testing (12 batches of 10, via subagents in parallel)
Stage 8: Synthesis & Final Audit Report (.md deliverable)
```

## Execution Instructions

### Step 0: Read the Instrument

Before anything else, read the entire uploaded assessment instrument. Identify:
- The instrument's name and stated purpose
- All dimensions/scales/factors
- All items (questions) and their assigned dimensions
- The response format (Likert scale, forced choice, ranking, etc.)
- The scoring algorithm
- Any classification/typology system (archetypes, types, profiles)
- The intended population

Confirm your understanding with the user before proceeding. Ask: "I've identified [N] dimensions, [N] items, and a [type] classification system. Should I proceed with the full validation pipeline?"

### Step 1: Construct & Content Validity Analysis

Read `references/stage-prompts.md` — Section 1.

Execute the Stage 1 analysis prompt against the uploaded instrument. Produce the full analysis conversationally. Key deliverables:
- Construct definition clarity ratings (1-5 per dimension)
- Content coverage matrix
- Face validity and social desirability assessment
- Nomological network mapping
- Overall construct validity judgment table

### Step 2: Item-Level Quality Analysis

Read `references/stage-prompts.md` — Section 2.

Execute the Stage 2 analysis. Key deliverables:
- Item quality audit (all items evaluated)
- Problematic item inventory table (minimum 20% of items)
- Dimension-level item set evaluation
- Response scale assessment
- Overall item quality grade (A-F)

### Step 3: Dimensional Structure & Classification Validity

Read `references/stage-prompts.md` — Section 3.

Execute the Stage 3 analysis. Key deliverables:
- Predicted factor structure and pattern matrix
- Inter-dimension correlation matrix with flags
- Alternative factor structures
- Classification/typology algorithm analysis
- Structural validity verdict

### Step 4: Comparative Analysis

Read `references/stage-prompts.md` — Section 4.

Execute the Stage 4 analysis. Compare against established instruments relevant to the instrument's domain. For career assessments, compare against MBTI, DISC, CliftonStrengths, Hogan, Holland/RIASEC, NEO-PI-R, Career Anchors, LAB Profile, and Predictive Index. For other instrument types, identify and compare against the 5-9 most relevant established instruments in that domain.

Key deliverables:
- Instrument-by-instrument comparison
- Incremental validity analysis
- Competitive positioning matrix
- Originality assessment

### Step 5: Bias, Fairness & Cross-Cultural Analysis

Read `references/stage-prompts.md` — Section 5.

Execute the Stage 5 analysis. Key deliverables:
- Theoretical DIF analysis across gender, culture, age, neurodivergence, SES
- Structural fairness analysis
- Language and accessibility analysis
- Adverse impact predictions
- Top 15 items needing fairness revision

### Step 6: Persona Generation

This is where the skill diverges from the reference template. Instead of using pre-built career personas, generate 120 custom personas tailored to THIS specific instrument.

Read `references/persona-generation-guide.md` for the persona structure template and category system.

Generate 120 personas organized into 6 categories (20 each):
- **Category A (1-20): Career Stage Spectrum** — early career through late career, tailored to the instrument's target population
- **Category B (21-40): Industry & Function Diversity** — spanning industries and roles relevant to this instrument's domain
- **Category C (41-60): Psychological Profile Variations** — Big Five extremes, motivation differences, meta-aware respondents
- **Category D (61-80): Edge Cases & Stress Tests** — impression managers, disengaged completers, acquiescence bias, career changers, neurodivergent professionals, contradictory profiles
- **Category E (81-100): Demographic Diversity** — gender, culture, disability, SES, non-traditional backgrounds
- **Category F (101-120): Classification Stress Tests** — "pure type" profiles engineered to test each classification category, tie-breakers, flat profiles, random responders

Each persona must include:
- ID, name, demographics
- Career context relevant to the instrument
- Big Five approximation and motivational drivers
- Testing purpose (what this persona reveals about the instrument)
- Expected response tendencies

Save the generated personas to a workspace file for reference by subagents.

### Step 7: Persona Testing via Subagents

This is the most intensive stage. Spawn 12 subagent batches in parallel.

**Batch assignment:**

| Batch | Personas | Category Focus |
|-------|----------|----------------|
| A | 1-10 | Early Career |
| B | 11-20 | Rising & Mid-Career |
| C | 21-30 | Industry Diversity 1 |
| D | 31-40 | Industry Diversity 2 |
| E | 41-50 | Psychological Profiles 1 |
| F | 51-60 | Psychological Profiles 2 |
| G | 61-70 | Edge Cases 1 |
| H | 71-80 | Edge Cases 2 |
| I | 81-90 | Edge Cases 3 + Demographics 1 |
| J | 91-100 | Demographics 2 |
| K | 101-110 | Demographics 3 + Pure Types 1 |
| L | 111-120 | Pure Types 2 + Stress Tests |

**For each subagent batch, provide this prompt:**

```
You are a research psychologist conducting a simulated validation study. You will role-play 10 distinct professional personas, answering ALL assessment questions as each persona would authentically respond.

INSTRUMENT TO VALIDATE:
[Paste or reference the full instrument]

CRITICAL METHODOLOGY RULES:
1. Authentic responses based on each persona's psychological profile — not what the assessment "wants"
2. Use the full response scale unevenly (real humans don't cluster)
3. Include 2-3 intentional inconsistencies per persona (real humans are inconsistent)
4. Serve each persona's TESTING PURPOSE — the goal is to stress-test the instrument

PERSONAS FOR THIS BATCH:
[Paste the 10 persona definitions]

FOR EACH PERSONA, PROVIDE:

Part 1: Response Sheet
| Question # | Response | Brief Rationale |

Part 2: Expected vs. Predicted Classification
- What classification SHOULD this persona receive?
- What will the algorithm ACTUALLY assign?
- If different, explain why

Part 3: Scoring Algorithm Execution
- Calculate all dimension raw scores
- Run the classification algorithm exactly as documented
- Report assigned type/profile with confidence level

Part 4: Validity Assessment
- Did the algorithm produce the expected result?
- What does this persona's testing purpose reveal?

BATCH SUMMARY (after all 10):
1. Classification accuracy (X/10)
2. Patterns of failure
3. Instrument weaknesses exposed
4. Top 3 findings
```

**Execution strategy:**
- Spawn all 12 batches simultaneously as subagent tasks
- Save each batch's results to `workspace/batch-[A-L]/results.md`
- As batches complete, collect their batch summaries
- If any batch fails, retry it once before proceeding without it

### Step 8: Synthesis & Final Audit Report

Read `references/synthesis-template.md` for the full report structure.

Once all (or most) subagent batches have returned, synthesize everything into the final audit report.

Collect:
- Key findings from Stages 1-5 (already in conversation context)
- Batch summaries from all 12 persona testing batches
- Cross-batch patterns

Produce the final `.md` report with these sections:

**A. Executive Summary** — Overall rating (1-10), top 3 strengths, top 3 weaknesses, readiness level

**B. Psychometric Scorecard** — 14-criterion rating table (1-5 each)

**C. Persona Testing Meta-Analysis** — Classification accuracy, failure patterns, most revealing results

**D. Critical Issues** — Priority-ordered issues requiring immediate attention

**E. Improvement Roadmap** — Phase 1 (critical fixes), Phase 2 (pilot study design), Phase 3 (norm development), Phase 4 (publication readiness)

**F. Scoring Algorithm Revision** — Specific implementable improvements

**G. Comparative Positioning** — Honest market positioning recommendations

**H. Final Verdict** — 750-word narrative assessment in peer-reviewed style

Save the report to the output directory and present it to the user.

## Output

The final deliverable is a `.md` file named `[instrument-name]-psychometric-audit.md` saved to `/mnt/user-data/outputs/`.

## Error Handling

- If the instrument has no scoring algorithm: skip classification testing in Stage 7, focus on item-level and construct analysis
- If the instrument has fewer than 20 items: reduce persona count to 60 (skip Categories B and E)
- If subagent batches fail: retry once, then proceed with available results and note gaps in the report
- If the instrument type is ambiguous: ask the user to clarify before generating personas

## Timing Expectations

- Stages 1-5: ~10-15 minutes total (sequential)
- Stage 6: ~5 minutes (persona generation)
- Stage 7: ~15-25 minutes (parallel subagent execution)
- Stage 8: ~10 minutes (synthesis and report generation)
- Total: ~40-55 minutes for a complete validation
