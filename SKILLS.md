---
name: decision-model
description: |
  Helps users build a structured judgment model when they need to make a decision.
  
  Trigger Scenarios:
  - User says "Help me make a decision"
  - User says "Help me decide whether to..."
  - User says "Help me choose..."
  - User says "Help me evaluate..."
  - User says "Help me judge..."
  - User describes a decision-making scenario (e.g., "Should I hire this person?", "Is this project worth investing in?")
  
  This skill is based on the Mechanical Judgment Model from Kahneman's "Noise." It eliminates random noise in human intuition through a standardized linear model, providing more stable and reproducible decision outcomes.
---

# Decision-Judgment Model Skill

## Core Objective

Help users establish a structured decision model by transforming vague judgments into a quantifiable process through the following steps:

1. **Parse Decision Scenario** — Clarify the decision goal (Binary, Ranking, Scoring).
2. **Evaluate Decision Attributes** — Confirm importance and reversibility.
3. **Identify Predictors** — Guide the user to find 6–8 key variables.
4. **Standardize Scoring** — Convert each factor into comparable standardized scores.
5. **Calculate Judgment Score** — Apply a Unit-Weight Model to derive the result.
6. **Provide Decision Recommendation** — Offer clear action advice based on thresholds.

## Workflow

### Step 1: Parse Decision Scenario

When a user presents a decision need, first clarify:

**Decision Goal Type:**
- **Binary**: Yes/No, Pass/Fail, Hire/Don't Hire.
- **Ranking**: Prioritizing multiple options.
- **Scoring**: Evaluating a single entity.

**Key Questions:**
- "What kind of decision do you need to make?"
- "How high is the importance of this decision? (High/Medium/Low)"
- "Is the decision reversible if it turns out to be wrong? (Reversible/Irreversible)"

**Importance-Reversibility Matrix:**
| | Reversible | Irreversible |
|---|---|---|
| **High Importance** | Experiment boldly; iterate fast | Proceed with extreme caution; consider worst-case scenarios |
| **Low Importance** | Decide quickly; don't overthink | Not worth significant time investment |

---

### Step 2: Identify Predictors

Guide the user to identify 6–8 predictive factors (variables) clearly related to the outcome.

**Selection Criteria (Must meet all three):**
1. **Clearly Related**: The factor has a clear logical connection to the decision outcome.
2. **Obtainable Pre-decision**: The information can be obtained before the decision is made.
3. **Relatively Objective**: Can be quantified or has clear evaluation standards.

**Reference for Common Factor Types:**

| Type | Description | Examples |
|------|------|------|
| Historical Performance | Past behavior or outcomes | Sales volume, project completion rate, historical ratings |
| Competency Indicators | Quantifiable data reflecting ability | Test scores, skill levels, years of experience |
| Alignment/Fit | Degree of synergy with needs or standards | Job fit, strategic alignment |
| Risk Indicators | Potential negative factors | Default records, failure count, negative feedback |
| Cost Factors | Resource investment related | Budget, time cost, manpower cost |
| Growth Potential | Future development space | Learning speed, growth trajectory, trainability |

**Guiding Phrases:**
- "What factors do you believe best predict the success of this decision?"
- "If you were making this judgment, what specific areas would you focus on?"
- "Are there any obvious red flags or green lights?"

---

### Step 3: Design Scoring Standards

Design a 1–5 or 1–10 scale for each factor.

**Scoring Standard Template:**
-Factor: [Factor Name]
-Meaning: [Specific definition]
-Scoring Criteria:

-5 Points: [Excellent / Fully compliant / Extremely low risk description]

-4 Points: [Good / Mostly compliant / Low risk description]

-3 Points: [Average / Partially compliant / Moderate risk description]

-2 Points: [Poor / Not very compliant / High risk description]

-1 Point: [Very poor / Completely non-compliant / Extremely high risk description]

**Notes:**
- Each score tier must have a clear, distinguishable description.
- Avoid overly broad middle tiers.
- Use objective indicators rather than subjective feelings whenever possible.

---

### Step 4: Data Collection and Scoring

**Scenario A: User has historical data**
- Ask for specific values for each factor.
- Use the standardization formula to convert to Z-scores.

**Scenario B: User has no historical data**
- Conduct subjective scoring on a 1–5 scale directly.
- Advise the user to score quickly based on intuition; do not overthink.

**Standardization Formula (For historical data):**
$$z_i = \frac{x_i - \mu_i}{\sigma_i}$$

Where:
- $x_i$ = Raw value
- $\mu_i$ = Historical mean
- $\sigma_i$ = Historical standard deviation
- $z_i$ = Standardized score (usually ranging from -3 to +3)

---

### Step 5: Calculate Judgment Score

**Unit-Weight Model Formula:**
$$\hat{Y} = \frac{\sum_{i=1}^{n} z_i}{n}$$

Or for 1–5 point scoring:
$$\hat{Y} = \frac{\sum_{i=1}^{n} score_i}{n}$$

**Features:**
- All factors are weighted equally.
- Simple, transparent, and less prone to overfitting.
- Kahneman’s research shows: Unit-weight models often outperform expert-assigned weights.

---

### Step 6: Set Decision Thresholds

Set thresholds based on the decision type:

**Binary Decision Thresholds:**
| Threshold Position | Applicable Scenario |
|---------|---------|
| Above Average (>0) | Requires aggressive screening (e.g., investment opportunities) |
| Average (=0) | Balanced decisions |
| Below Average (<0) | Conservative decisions (e.g., loan approvals) |

**Scoring Decision Reference:**
- Average Score ≥ 4.0: Strongly Recommended
- Average Score 3.0–4.0: Worth Considering
- Average Score 2.0–3.0: Proceed with Caution
- Average Score < 2.0: Not Recommended

---

### Step 7: Generate Judgment Report

Use the following template for the final output:

```markdown
## Judgment Report: [Decision Scenario]

### Predictive Factor Scoring
| Factor | Weight | Raw Value | Standardized Score |
|------|------|--------|-----------|
| [Factor 1] | Equal | [Value] | [Score] |
| [Factor 2] | Equal | [Value] | [Score] |
| ... | ... | ... | ... |

### Calculation Results
- **Judgment Score**: [X.XX]
- **Decision Threshold**: [X.XX]
- **Recommended Decision**: [Pass / Fail / Further Evaluation Required]

### Key Insights
- **Strongest Positive Factor**: [Factor X] — [Specific explanation]
- **Strongest Negative Factor**: [Factor Y] — [Specific explanation]
- **Risk Alerts**: [If any]

### Model Description
This judgment is based on the Mechanical Judgment Model from Kahneman's "Noise," eliminating random noise in human intuition.

⚠️ **Important Reminders**:
- If there is clear "Broken Leg Information" (extreme special cases the model cannot consider), please manually override.
- The model provides a reference; the final decision authority lies with you.
- For irreversible important decisions, it is recommended to add an additional review step.

### Checklist
- [ ] All factors were obtainable before the decision.
- [ ] Scoring standards are relatively objective.
- [ ] Worst-case scenarios have been considered.
- [ ] Confirmed that no obvious "Broken Leg Information" was missed.



Special Handling
Broken Leg Information (Override Rule)
If the following situations exist, the model result is for reference only and requires a manual override:

Extreme Negative Information: Such as fraud records, serious default, or ethical issues.

Extreme Positive Information: Such as top-tier industry experts, exclusive resources, or strategic-level cooperation.

Constraints Not Considered by the Model: Such as compliance requirements, policy changes, or sudden crises.


Multi-Option Ranking
When multiple options need to be ranked:

Run the model separately for each option.

Sort options from highest to lowest judgment score.

Output the ranking results and an analysis of score differences.


Sensitivity Analysis
Explain to the user:

How changing the score of a certain factor would affect the result.

Which factors are most sensitive to the outcome.

Under what circumstances a re-evaluation is recommended.


Output Principles
Transparent: Show all calculation processes and assumptions.

Concise: Avoid overly complex mathematical expressions.

Actionable: Give clear next-step suggestions.

Humble: Be clear about the model's limitations and applicability boundaries.


Example Dialogue
User: "Help me decide whether to hire this Product Manager candidate."

Assistant:

Certainly, I will help you establish a structured hiring decision model.


Step 1: Clarify Decision Attributes

Decision Type: Binary (Hire/Don't Hire)

Importance: High (The cost of a bad hire is high)

Reversibility: Partially Reversible (Can be terminated after the probation period, but with associated costs)


Step 2: Identify Predictors
Based on the Product Manager role, I suggest focusing on the following factors (you can adjust these as needed):


Years of Product Experience

Case Analysis/Practical Performance

Communication and Collaboration Skills

Industry Alignment

Learning Ability/Potential

Salary Expectation Alignment

Does this framework seem appropriate to you? Which factors should we add or remove?

(Continue guiding the user to complete scoring and calculation)

