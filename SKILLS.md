name: judgment
description: Based on Kahneman's "Noise" judgment model, helps users make low-noise, high-consistency decisions. Replaces noisy human intuition with standardized scoring and mechanical rules.
argument-hint: "[Decision scenario description]"
disable-model-invocation: true
---

# /judgment — Mechanical Judgment Assistant

Based on Daniel Kahneman's judgment model theory in "Noise," helps users build simple, noise-free decision rules.

Core principle: Simple models make better judgments than human experts because they eliminate noise in human judgment (emotional fluctuations, fatigue, inconsistency).

## Input

`$ARGUMENTS` is a description of the decision scenario the user needs to make, such as:
- "Whether to hire this candidate"
- "Whether to make this investment"
- "Which supplier to choose"

## Execution Steps

### Step 1: Understand the Decision Scenario

1. Parse the decision scenario described by the user
2. Clarify the decision objective (binary choice, ranking, scoring, etc.)
3. Confirm the importance and reversibility of the decision

### Step 2: Identify Predictive Factors

Based on the user scenario, guide the user to identify 6-8 key predictive factors (variables):

**Selection Criteria:**
- Obviously related to the outcome
- Can be obtained before the decision
- Relatively objective and quantifiable

**Example Factor Types:**
- Historical performance data
- Capability indicators
- Match degree scores
- Risk indicators
- Cost factors

### Step 3: Build the Judgment Model

Use the standardized equal-weight model (recommended by Kahneman):

**Formula:**
markdown
Judgment Score = Average( (Factor1-Mean1)/StdDev1, (Factor2-Mean2)/StdDev2, ... )


**If historical statistical data is lacking, use the simplified version:**
Judgment Score = (Factor1Score + Factor2Score + ... + FactorNScore) / N


Recommended scoring range for each factor: 1-5 points or 1-10 points

### Step 4: Set Decision Thresholds

Set thresholds based on decision type:

| Decision Type | Threshold Recommendation | Explanation |
|---------|---------|------|
| Conservative (e.g., hiring, investment)| ≥ 0.5 | Half standard deviation above average |
| Balanced | ≥ 0 | Above average |
| Lenient (e.g., preliminary screening)| ≥ -0.5 | Accept below average |

### Step 5: Execute Judgment

1. Collect actual values or scores for each factor
2. Calculate standardized scores
3. Calculate final judgment score
4. Compare with threshold to derive decision recommendation

### Step 6: Output Results

Generate structured judgment report:

```markdown
## Judgment Report: [Decision Scenario]

### Predictive Factor Scores
| Factor | Weight | Raw Value | Standardized Score |
|------|------|--------|-----------|
| Factor1 | Equal | X | Z1 |
| Factor2 | Equal | Y | Z2 |
| ... | ... | ... | ... |

### Calculation Results
- **Judgment Score**: X.XX
- **Decision Threshold**: X.XX
- **Recommended Decision**: [Pass/Fail/Needs Further Evaluation]

### Key Insights
- Strongest positive factor: [FactorX]
- Strongest negative factor: [FactorY]
- Risk warnings: [if any]

### Model Explanation
This judgment is based on Kahneman's mechanical judgment model in "Noise," eliminating random noise in human intuition.
**Note**: If there is clear "broken leg information" (extreme special circumstances the model cannot consider), please manually override.
Usage Example
User Input:

/judgment Whether to hire this product manager candidate
System Execution:

Identify scenario: Hiring decision (conservative type)
Suggest factors: Years of experience, case analysis score, communication ability, education background, industry match, salary match
Guide user to score each factor
Calculate judgment score
Provide pass/fail recommendation
Core Advantages
Consistency: Same input always produces same output
No Emotional Interference: Not affected by fatigue, mood, or time
Transparent and Explainable: Contribution of each factor is clearly visible
Iteratively Optimizable: Adjust factors and thresholds based on result feedback
Notes
This model applies to predictive judgments (predicting future performance based on existing information)
Not applicable to creative decisions (requiring breakthrough thinking)
When "broken leg information" exists that the model cannot consider, manual override is allowed
Recommend regularly verifying model accuracy with actual results
Theoretical Basis
Daniel Kahneman "Noise: A Flaw in Human Judgment" Chapter 9, Chapter 10:

Simple mechanical models generally outperform human judgment
Equal-weight models often outperform expert weighting
Eliminating noise is key to improving judgment accuracy