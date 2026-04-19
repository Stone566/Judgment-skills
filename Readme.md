# ⚖️ Judgment — Mechanical Decision Framework

> **"Algorithms may not be perfect, but they are consistent. Human judgment, however, is full of noise."**
> — Inspired by Daniel Kahneman’s *Noise: A Flaw in Human Judgment*.

This repository contains a structured framework designed to eliminate **stochastic noise**—the random variability in human judgment caused by mood, fatigue, or irrelevant environmental factors. By converting intuitive "gut feelings" into a quantized, linear mechanical model, you can achieve more stable and reproducible outcomes for critical decisions.

---

## 🧠 Core Philosophy

In *Noise*, Kahneman demonstrates that **simple mechanical models often outperform human experts.** This tool helps you build a "Noise-Free" decision model through:
1.  **De-biasing:** Standardizing the criteria before evaluating the subject.
2.  **Consistency:** Ensuring that the same input always yields the same output.
3.  **Equal Weighting:** Applying a "Unit-Weight Model," which often proves more robust than expert-assigned weights.

---

## 🛠️ The 6-Step Workflow

### 1. Scenario Analysis
Define the objective and the nature of the decision.

**Decision Types:**
* **Binary:** Hire/No Hire, Invest/No Invest.
* **Ranking:** Prioritizing multiple options.
* **Scoring:** Evaluating a single entity against a standard.

### 2. Identify Predictors
Select 6-8 variables that are clearly correlated with the outcome, available before the decision, and relatively objective.

### 3. Design Scoring Standards
Create a 1-5 or 1-10 scale for each predictor. Each level must have a distinct, objective description to minimize subjective "rating noise."

### 4. Data Collection & Standardization
If historical data is available, convert raw values ($x_i$) into Z-scores:
$$z_i = \frac{x_i - \mu_i}{\sigma_i}$$

### 5. Calculate Judgment Score ($\hat{Y}$)
Apply the **Unit-Weight Model**:
$$\hat{Y} = \frac{\sum_{i=1}^{n} score_i}{n}$$

### 6. Set Thresholds
Determine your "Pass/Fail" line based on the decision's risk profile:
* **Conservative (High Risk):** Score > 4.0/5.0
* **Balanced:** Score > 3.0/5.0

---

## ⚠️ The Broken Leg Rule (Override)

Mechanical models should be followed 99% of the time. However, you may **override** the model if you encounter "Broken Leg" information—rare, decisive facts the model was not designed to see (e.g., a candidate has perfect scores but has committed serious fraud).

---

## 📝 Usage
Import the logic from `SKILL.md` into your LLM (Claude, ChatGPT) to activate the `/judgment` command.