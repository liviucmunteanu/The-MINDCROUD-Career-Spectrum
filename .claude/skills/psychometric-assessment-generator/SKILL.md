---
name: psychometric-assessment-generator
description: >
  Generate professional psychometric assessments grounded in AERA/APA/NCME Standards and ITC Guidelines. Produces complete instruments with items, scoring keys, interpretation guides, administration manuals, report templates, and debrief guides. Supports personality profiling (Big Five, HEXACO), cognitive/aptitude tests, attitudes/values surveys (market research, brand perception, NPS), and competency assessments (360 feedback, BARS, SJTs). Handles multilingual cross-cultural adaptation. Trigger whenever the user wants to create any psychometric test, assessment, survey instrument, personality test, aptitude test, competency assessment, 360 feedback tool, engagement survey, market research survey, brand perception study, hiring assessment, coaching assessment, leadership assessment,values inventory, attitude scale, or situational judgment test. Also trigger on "assessment design", "test construction", "scale development", "item writing", or "psychometrics"
---

# Psychometric Assessment Generator

This skill generates professional-grade psychometric assessments grounded in the
AERA/APA/NCME Standards for Educational and Psychological Testing and ITC Guidelines.
Every assessment produced follows a rigorous pipeline that ensures construct validity,
reliability, fairness, and practical utility.

## Before You Begin

Read the relevant reference files based on the assessment request:

| Reference File | Read When |
|---|---|
| `references/item-construction.md` | Every assessment (core rules) |
| `references/assessment-types.md` | To select the right format/framework for the domain |
| `references/scoring-and-norms.md` | Every assessment (scoring engine design) |
| `references/cross-cultural.md` | Multilingual or cross-cultural assessments |
| `references/deliverables.md` | Generating admin manuals, reports, debrief guides |
| `references/quality-checklist.md` | Final quality audit before delivery |

Always read `item-construction.md` and `scoring-and-norms.md`. Read the others as needed.

---

## Step 1: Gather Required Inputs

Before generating anything, collect these seven categories of specification from the user.
Do not proceed without answers for at least items 1–5. Items 6–7 have sensible defaults.

### 1. PURPOSE & STAKES (Required)
- What is this assessment for? (selection, development, research, market insight, coaching)
- What decisions will be made from results? (hire/no-hire, development planning, segmentation)
- Stakes level: HIGH (employment, certification) → requires α ≥ .90, proctored admin, fairness docs
  MEDIUM (development, coaching) → requires α ≥ .80, flexible admin
  LOW (research, exploration) → requires α ≥ .70, self-administered OK

### 2. CONSTRUCT DEFINITION (Required)
- What exactly are you trying to measure? (e.g., "emotional intelligence in sales leaders")
- Theoretical framework if any (e.g., Big Five, Goleman's EI model, custom competency model)
- Dimensionality: how many subscales/factors?
- What is this construct NOT? (discriminant boundaries)

### 3. TARGET POPULATION (Required)
- Who takes this assessment? (age range, education level, profession, cultural context)
- Reading level requirement (default: 8th grade for general, 6th grade for broad populations)
- Languages needed
- Special accommodations needed (accessibility, time extensions)

### 4. ASSESSMENT TYPE (Required)
- Personality/psychographic profiling
- Cognitive/aptitude testing
- Attitudes, preferences & values (market research)
- Behavioral/competency-based (360, BARS, SJT)
- Hybrid (specify combination)

### 5. ITEM FORMAT (Required — suggest based on type if user is unsure)
- Likert scale (5-point or 7-point; agreement, frequency, or intensity anchors)
- Forced-choice (pairs, triads, or quads — requires Thurstonian IRT scoring)
- Semantic differential (bipolar adjective pairs)
- Situational Judgment Test (scenarios with ranked response options)
- Multiple-choice (for cognitive/aptitude)
- Behavioral frequency rating (for 360/competency)
- Mixed format

### 6. SCALE LENGTH (Default: 60–90 items)
- Short: 15–25 items (quick screening, commercial use)
- Medium: 30–60 items (balanced depth and completion rate)
- Long: 60–120 items (rigorous profiling, maximum reliability)
- Specify items per subscale if known (minimum 5, recommended 8–10)

### 7. DELIVERABLES (Default: all)
- Assessment instrument (items + response format)
- Scoring key with reverse-score mapping
- Score interpretation guide (with score ranges and narrative descriptors)
- Administration manual
- Individual report template
- Group report template
- Debrief/feedback session guide
- Cross-cultural adaptation guide (if multilingual)

---

## Step 2: Design the Assessment Architecture

Once inputs are gathered, design the architecture before writing any items.

### 2a. Build the Test Blueprint

Create a structured blueprint that maps:

```
CONSTRUCT: [Name]
├── DIMENSION 1: [Name] — [Definition] — [Weight: X%]
│   ├── Facet 1a: [Name] — [N items] — [Format]
│   └── Facet 1b: [Name] — [N items] — [Format]
├── DIMENSION 2: [Name] — [Definition] — [Weight: X%]
│   ├── Facet 2a: ...
│   └── Facet 2b: ...
└── VALIDITY SCALES (if applicable)
    ├── Social Desirability: [N items]
    ├── Infrequency/Careless Responding: [N items]
    └── Consistency Check: [N item pairs]
```

Rules for the blueprint:
- Minimum 3 dimensions for multidimensional constructs
- Minimum 5 items per dimension (8–10 preferred for α ≥ .80)
- Generate 2× the items needed, then select the best during quality review
- Weight dimensions by theoretical importance and practical utility
- Include 3–5 validity/attention check items for assessments > 30 items

### 2b. Select Response Format

Follow the decision tree in `references/item-construction.md` to select the optimal
response format. Key principles:

- Likert (5 or 7 point) = default for attitudes, personality, self-report
- Forced-choice = when faking resistance matters (selection contexts)
- Semantic differential = brand perception, concept evaluation
- SJT = competency assessment, behavioral prediction
- Multiple-choice = cognitive ability, knowledge testing

### 2c. Plan Scoring Architecture

Refer to `references/scoring-and-norms.md` for the full scoring decision tree.
Key decisions at this stage:

- CTT (simple, works with small samples) vs IRT (sample-invariant, adaptive-ready)
- Norm-referenced (compare to population) vs criterion-referenced (compare to standard)
- Score transformation: T-scores (clinical), stens (occupational), stanines (educational),
  percentiles (lay communication)
- Ipsative warning: if using forced-choice format with classical scoring, flag that
  scores are ipsative and cannot be compared between individuals

---

## Step 3: Write Assessment Items

This is the core generation step. Follow ALL rules from `references/item-construction.md`.

### Item Generation Protocol

For each dimension/facet in the blueprint:

1. **Write 2× the target number of items** (e.g., if you need 8, write 16)
2. **Apply the Universal Item Rules** (see reference file):
   - One idea per item (no double-barreled items)
   - 8th grade reading level or below
   - Avoid leading language, jargon, idioms, culturally specific references
   - Use behavioral/observable language, not evaluative abstractions
   - Vary sentence structure and length naturally
3. **Balance item keying**:
   - Default: ~75% positively keyed, ~25% negatively keyed (antonym-based, NOT negation)
   - If forced-choice: match items within blocks on social desirability level
   - If targeting faking resistance: use forced-choice with Thurstonian IRT
4. **Add validity items** (for instruments > 30 items):
   - 2–3 infrequency items ("I have traveled to every country on Earth")
   - 2–3 consistency pairs (semantically equivalent items placed far apart)
   - Optional: social desirability scale items (6–10 items)
5. **Sequence items properly**:
   - Begin with easy, non-threatening items
   - Place sensitive items in the middle third
   - Group by format, not by construct (to reduce transparent factor structure)
   - Randomize within format groups
   - Place attention checks at 25%, 50%, and 75% progress points

### Item Output Format

Present each item in this structured format:

```
ITEM [ID]: [Item text]
  Dimension: [Dimension name]
  Facet: [Facet name]
  Keying: [Positive / Negative / Attention Check / Validity]
  Response Format: [Likert-5 / Likert-7 / FC-pair / SD-7 / MC-4 / etc.]
  Scoring: [1-2-3-4-5 or 5-4-3-2-1 for reverse-scored]
  Rationale: [Why this item measures the target construct]
```

---

## Step 4: Build the Scoring Key

For every assessment, produce a complete scoring key document:

### Scoring Key Structure

```markdown
# SCORING KEY: [Assessment Name]

## Response Coding
- [Describe response option → numeric value mapping]
- [List all reverse-scored item IDs with reversed coding]

## Subscale Computation
- [Dimension 1]: Sum/Mean of items [ID list] → Raw Score Range [min–max]
- [Dimension 2]: ...

## Score Transformations
- [Transformation type and formula]
- [Norm table reference or inline norms]

## Validity Indicators
- Infrequency Score: Flag if ≥ [threshold] items endorsed
- Consistency Index: Flag if [N]+ paired items show |diff| ≥ [threshold]
- Social Desirability: Report raw score; flag if > [threshold] (95th percentile)
- Completion Rate: Flag if > [%] items missing

## Interpretation Ranges
| Score Range | Classification | Narrative Descriptor |
|-------------|---------------|---------------------|
| [range]     | [label]       | [description]       |
```

---

## Step 5: Generate Supporting Deliverables

Refer to `references/deliverables.md` for full templates. Generate each requested deliverable:

### Assessment Instrument Document
- Cover page with assessment name, version, date, copyright notice
- Standardized instructions for respondents
- All items in administration order with response options
- Time estimate and completion guidance

### Administration Manual
See `references/deliverables.md` § Administration Manual for the 12-section template.

### Score Interpretation Guide
See `references/deliverables.md` § Interpretation Guide for the structured template.

### Individual Report Template
See `references/deliverables.md` § Individual Report for the 8-section template.

### Group Report Template
See `references/deliverables.md` § Group Report for the 6-section template.

### Debrief/Feedback Session Guide
See `references/deliverables.md` § Debrief Guide for the structured session plan.

---

## Step 6: Cross-Cultural Adaptation (If Multilingual)

When the assessment needs to work across languages or cultures, follow the full
ITC-compliant process in `references/cross-cultural.md`. The minimum requirements are:

1. Double-translation and reconciliation (NOT back-translation alone)
2. Expert committee review for conceptual, semantic, idiomatic, and experiential equivalence
3. Cognitive debriefing with 30–40 target-language respondents
4. DIF analysis plan across demographic groups
5. Measurement invariance testing plan (configural → metric → scalar)
6. Cultural response style documentation (ERS, MRS, acquiescence patterns)

---

## Step 7: Quality Audit

Before delivering the final assessment, run every item and every deliverable through
the quality checklist in `references/quality-checklist.md`. This checklist operationalizes
the difference between a 5/10 and a 9+/10 assessment.

The audit covers:
- Item-level quality (clarity, reading level, bias, keying balance)
- Scale-level quality (reliability projections, content coverage, factor structure)
- Instrument-level quality (flow, timing, face validity, respondent experience)
- Deliverable quality (manual completeness, report actionability, debrief structure)
- Ethical compliance (informed consent, data privacy, qualified user requirements)

---

## Output Format

Deliver the complete assessment as a structured Markdown document with clear sections.
Use the following top-level structure for the main instrument file:

```markdown
# [ASSESSMENT NAME] v1.0

## Assessment Overview
[Purpose, construct, target population, theoretical framework]

## Test Blueprint
[Dimensions, facets, item counts, weights]

## Administration Instructions
[Standardized instructions for administrator and respondent]

## Assessment Items
[All items in administration order with response formats]

## Scoring Key
[Complete scoring instructions, reverse-score map, subscale computation]

## Score Interpretation Guide
[Score ranges, classifications, narrative descriptors]

## Psychometric Specifications
[Target reliability, validity evidence plan, norming recommendations]

## Ethical Use Guidelines
[Qualified user level, informed consent requirements, data handling]
```

Generate additional deliverable files separately when requested (admin manual, report
templates, debrief guide, cross-cultural adaptation guide).

---

## Critical Reminders

1. **Never reuse copyrighted items.** All items must be original. Draw inspiration from
   established frameworks (Big Five, HEXACO, VIA, competency models) but write all items
   from scratch. Reference public-domain item pools (IPIP) for structure only.

2. **Match rigor to stakes.** High-stakes = maximum reliability, fairness documentation,
   proctored admin. Low-stakes = prioritize face validity and actionability.

3. **Explain limitations honestly.** An AI-generated assessment has NOT been empirically
   validated. Always include a "Validation Recommendations" section specifying the
   sample sizes and analyses needed for proper validation (pilot N=100–300, validation
   N=300+, cross-validation on independent sample).

4. **Generate 2× items, present the best.** Write twice as many items as needed internally,
   then select the strongest based on the quality checklist criteria. Present only the
   final selected items to the user, but mention that a larger initial pool was considered.

5. **Default to positive keying with alternative bias controls** rather than heavy use of
   reverse-scored items (which often create artifactual factors). Use ~75/25 positive/negative
   ratio with antonym-based reversal when needed.
