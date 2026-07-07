# Scoring and Norms

This reference covers scoring methodology selection, score transformations, norm tables,
and cut-score setting. Consult for every assessment generated.

## Table of Contents
1. Scoring Theory Selection (CTT vs IRT)
2. Score Transformation Formulas
3. Norm-Referenced vs Criterion-Referenced
4. Subscale and Composite Score Computation
5. Cut-Score Setting Methods
6. Score Reporting Best Practices
7. Validity Indicator Scoring

---

## 1. Scoring Theory Selection

### Classical Test Theory (CTT)
**Use when**: Sample size < 300, simple scoring is preferred, no adaptive testing needed,
or the assessment is for development/coaching (not high-stakes selection).

- **Model**: X = T + E (observed = true score + error)
- **Item difficulty (p-value)**: Proportion answering correctly. Optimal range: .30–.70
- **Item discrimination**: Point-biserial correlation with total score.
  ≥ .30 = good, ≥ .20 = acceptable, < .15 = consider removing
- **Corrected item-total correlation**: Same but removes the target item from the total.
  Minimum ≥ .30 for retention, ideally ≥ .40
- **Reliability**: Cronbach's α (assumes tau-equivalence) or McDonald's ω (preferred,
  no tau-equivalence assumption)
- **SEM**: SEM = SD × √(1 − α). Confidence interval: Score ± 1.96 × SEM for 95% CI
- **Sample size**: 100–200 examinees sufficient for stable statistics
- **Limitation**: Item statistics are sample-dependent — different samples produce
  different p-values and discriminations

### Item Response Theory (IRT)
**Use when**: Sample size ≥ 250, adaptive testing is planned, cross-form equating is
needed, or maximum psychometric precision is required.

- **1PL/Rasch model**: P(correct) = f(θ − b). Only difficulty parameter.
  Sample size: 100–200. Use for: homogeneous items, educational measurement
- **2PL model**: P(correct) = f(a(θ − b)). Adds discrimination parameter.
  Sample size: 250–500. Use for: personality, attitude scales
- **3PL model**: P(correct) = c + (1−c) × f(a(θ − b)). Adds guessing parameter.
  Sample size: 500–1,000+. Use for: multiple-choice ability tests

**IRT advantages**:
- Sample-invariant item parameters (once calibrated)
- Item-level precision via information functions
- Enables computerized adaptive testing (CAT)
- Enables cross-form equating
- Required for Thurstonian forced-choice scoring
- Required for Bookmark standard-setting method

**IRT parameters**:
| Parameter | Symbol | Good Range | Meaning |
|-----------|--------|------------|---------|
| Difficulty | b | −2.0 to +2.0 | Where on the ability scale the item is most informative |
| Discrimination | a | 0.80 to 2.50 | How sharply the item differentiates ability levels |
| Guessing | c | 0.00 to 0.25 | Lower asymptote (chance of guessing correctly) |

### Decision Matrix
| Factor | Choose CTT | Choose IRT |
|--------|-----------|------------|
| Sample size | < 250 | ≥ 250 |
| Adaptive testing needed | No | Yes |
| Cross-form equating | Not needed | Needed |
| Forced-choice format | No (unless Thurstonian) | Yes (Thurstonian IRT) |
| Technical audience | General | Psychometrician available |
| Reporting simplicity | Priority | Can handle complexity |

---

## 2. Score Transformation Formulas

All transformations start from the z-score: **z = (X − M) / SD**

### Standard Score Transformations Table

| Scale | Formula | Mean | SD | Typical Range | Domain |
|-------|---------|------|----|---------------|--------|
| z-score | z = (X − M) / SD | 0 | 1 | −3 to +3 | Statistical analysis |
| T-score | T = 10z + 50 | 50 | 10 | 20–80 | Clinical, personality (MMPI) |
| Stanine | Round(2z + 5) | 5 | 2 | 1–9 | Educational assessment |
| Sten | Round(2z + 5.5) | 5.5 | 2 | 1–10 | Occupational personality (16PF, OPQ) |
| IQ-type | 15z + 100 | 100 | 15 | 55–145 | Intelligence, cognitive ability |
| Scaled score | 3z + 10 | 10 | 3 | 1–19 | Subtest scores (Wechsler) |
| NCE | 21.06z + 50 | 50 | 21.06 | 1–99 | Educational (equal interval percentiles) |

### Percentile Ranks
- Derived from cumulative normal distribution: Percentile = Φ(z) × 100
- **Critical warning**: Percentiles are ORDINAL, not interval. The difference between
  the 50th and 60th percentile ≠ the difference between the 90th and 95th.
- Never average percentile ranks directly — convert to z-scores or NCEs first
- Use for lay communication only; use standard scores for analysis

### Recommended Score Type by Domain
| Assessment Domain | Primary Score | Communication Score |
|---|---|---|
| Clinical personality (MMPI-style) | T-score | Percentile |
| Occupational personality (16PF-style) | Sten | Descriptive band |
| Intelligence/cognitive ability | IQ-type (M=100, SD=15) | Percentile + classification |
| Educational achievement | Stanine or Scaled Score | Percentile + band |
| Competency/360 feedback | Raw mean (1–5 scale) | Gap score (self vs others) |
| Market research/NPS | Raw score | Category (Promoter/Passive/Detractor) |
| Attitude scales | Mean score per dimension | Descriptive label |

---

## 3. Norm-Referenced vs Criterion-Referenced

### Norm-Referenced Scoring
Compares individual to a reference group. The score's meaning comes from relative standing.
- **When to use**: Personality assessment, cognitive ability, any construct where
  "how much compared to others" is the relevant question
- **Norm group requirements**:
  - Representative of the intended population
  - Sufficiently large: minimum 100 per demographic subgroup, ideally 300+
  - Recent: norms should be updated every 5–10 years (Flynn effect for IQ; cultural
    shifts for personality/attitudes)
  - Documented: demographics, collection dates, geographic scope

### Criterion-Referenced Scoring
Compares individual to a defined performance standard. The score's meaning comes from
what the person can or cannot do.
- **When to use**: Competency assessment ("meets standard"), certification exams,
  mastery learning, performance benchmarking
- **Requires**: Clearly defined performance levels (e.g., Below Expectations / Meets /
  Exceeds) and a defensible cut-score (see §5)

### Ipsative Scoring (Forced-Choice Classical)
- **What it is**: Scores are relative within the individual — they show which traits
  are highest/lowest FOR THIS PERSON, but cannot compare across people
- **Why it's problematic**: Constant sum constraint means if one trait goes up, another
  must go down. This distorts correlations, invalidates factor analysis, and prevents
  normative comparisons.
- **Solution**: Thurstonian IRT recovers normative scores from forced-choice data
- **If using classical forced-choice scoring**: Label all outputs as ipsative, explicitly
  state they cannot be used for between-person comparison, and recommend Thurstonian IRT
  for any application requiring normative scores

---

## 4. Subscale and Composite Score Computation

### Subscale Scores
For each subscale/dimension:
1. Identify all items belonging to the subscale
2. Reverse-score any negatively keyed items: reverse = (max + 1) − response
3. Compute: **Sum** (for maximum differentiation) or **Mean** (for interpretability
   on the original scale)
4. Check for missing data: if > 20% of items missing, flag subscale as unreliable
   If ≤ 20% missing: use person-mean imputation (replace missing with person's mean
   on available items in that subscale)

### Composite / Total Scores
- **Simple sum/mean**: Equal weight to all subscales. Use when theory doesn't specify
  differential importance.
- **Weighted composite**: Multiply subscale scores by theoretical or empirical weights.
  Use when some dimensions are more important for the criterion.
- **Profile-based**: Don't combine — report each subscale separately. Use for personality,
  360 feedback, and any multidimensional construct where the profile shape matters more
  than a total.
- **Rule of thumb**: If subscale intercorrelations are < .30, DO NOT create a total score —
  the dimensions are distinct constructs.

### Score Confidence Intervals
Always report scores with confidence intervals:
- 95% CI: Score ± 1.96 × SEM
- 90% CI: Score ± 1.645 × SEM (more practical, recommended for most applications)
- Interpretation: "The person's true score has a 90% probability of falling between
  [lower] and [upper]."
- **Display**: Use error bars on profile charts, shaded bands on score reports

---

## 5. Cut-Score Setting Methods

### Modified Angoff Method (Most Common)
1. Assemble 8–15 Subject Matter Expert (SME) panelists
2. Define the "minimally competent" candidate in behavioral terms
3. Round 1: Each panelist estimates P(minimally competent candidate answers correctly)
   for each item
4. Share item-level difficulty data and pass/fail impact data
5. Round 2: Panelists revise estimates with data in hand
6. Optional Round 3 for remaining disagreements
7. Cut score = Sum of averaged probabilities across items
8. Report: final cut, panelist agreement (SD), impact data (% pass/fail)

### Bookmark Method (IRT-Based)
1. Requires IRT-calibrated items
2. Arrange items in an Ordered Item Booklet (easy → hard by IRT difficulty)
3. Panelists read through items and place a "bookmark" at the point where a minimally
   competent candidate would have a 0.67 probability of answering correctly
4. Cut score = θ value corresponding to the bookmarked item
5. Advantages: More intuitive for panelists, accounts for item quality

### Contrasting Groups Method (Examinee-Centered)
1. SMEs classify a sample of examinees as "competent" or "not competent" (independent
   of test scores)
2. Plot score distributions for both groups
3. Cut score = intersection point of the two distributions
4. Best for: Situations where external competency judgments are available

### Borderline Group Method
1. SMEs identify examinees whose competence is "borderline"
2. Cut score = median test score of the borderline group
3. Requires large enough borderline sample for stability (typically 30+)

### For Non-Ability Assessments (Personality, Attitudes)
Cut-scores are less common but sometimes needed (e.g., "high potential" threshold):
- Use **percentile-based cutoffs**: Top 25%, Top 10%, etc.
- Or **standard deviation bands**: Above average (> +0.5 SD), Average (±0.5 SD),
  Below average (< −0.5 SD)
- Document that these are normative, not absolute, classifications

---

## 6. Score Reporting Best Practices

### Numeric Score Presentation
- Always pair numeric scores with **descriptive labels** (not just numbers)
- Example: "T-score: 62 (Above Average)" not just "T-score: 62"
- Use **classification bands** that map to score ranges:

| Band | z-score | T-score | Sten | Stanine | Percentile | Label |
|------|---------|---------|------|---------|------------|-------|
| Very Low | < −2.0 | < 30 | 1 | 1 | < 2 | Very Low |
| Low | −2.0 to −1.0 | 30–40 | 2–3 | 2–3 | 2–16 | Low |
| Below Average | −1.0 to −0.5 | 40–45 | 4 | 4 | 16–31 | Below Average |
| Average | −0.5 to +0.5 | 45–55 | 5–6 | 5 | 31–69 | Average |
| Above Average | +0.5 to +1.0 | 55–60 | 7 | 6 | 69–84 | Above Average |
| High | +1.0 to +2.0 | 60–70 | 8–9 | 7–8 | 84–98 | High |
| Very High | > +2.0 | > 70 | 10 | 9 | > 98 | Very High |

### Visual Score Presentation
- **Bar charts**: Best for comparing across dimensions. Use for profile reports.
- **Radar/spider plots**: Good for showing profile shape. Use for personality, competency.
- **Score bands with error bars**: Best for communicating uncertainty. Use for individual feedback.
- **Traffic light indicators**: Green/Amber/Red for criterion-referenced (meets/developing/does not meet)
- **Gap charts**: For 360 feedback (self vs others, or current vs target)

### Narrative Interpretation
For each score or profile pattern, provide:
1. **What it means**: Plain-language description of what the score indicates
2. **Behavioral implications**: How this might show up in daily behavior or performance
3. **Development considerations**: What the person could do to leverage or develop this area
4. **Contextual caveats**: Why the score should be considered alongside other information

---

## 7. Validity Indicator Scoring

### Social Desirability Scale
- Score: Sum of endorsed socially desirable items
- Flag: Score > 95th percentile of norm group
- Action: Note in report that results should be interpreted with caution; consider
  re-administration under conditions that reduce impression management motivation

### Infrequency Items
- Score: Count of infrequent items endorsed (items no attentive person would endorse)
- Flag: ≥ 2 out of 3 infrequency items endorsed
- Action: Invalidate protocol; results should not be interpreted

### Consistency Pairs
- Score: Mean absolute difference between paired items
- Flag: Mean |diff| > 2.0 on 5-point scale across 3+ pairs
- Action: Flag as potentially inconsistent; note in report; may indicate careless
  responding, poor reading comprehension, or ambivalence

### Completion Time
- Flag: Average < 2 seconds per item (suggests not reading items)
- Flag: Total time < 1/3 of expected administration time
- Action: Flag as potentially rushed; recommend re-administration

### Missing Data
- Flag: > 10% items missing → subscale-level concern
- Flag: > 20% items missing → protocol-level concern; do not score affected subscales
- Action: Report missing data rate; use person-mean imputation for ≤ 20% missing per subscale

### Response Pattern Analysis
- Flag: Straight-lining (same response for > 80% of consecutive items in a section)
- Flag: Zigzag pattern (alternating extreme responses: 1-5-1-5-1-5)
- Action: Flag as potentially invalid; recommend re-administration
