## Validator Design

### Scoring and Evaluation Methodology

Validators run the reference scoring implementation (open-source). For each miner:

```python
def calculate_miner_weight(miner):
    # Usage: share of total network invocations (last 7 days)
    usage_score = miner.invocations / total_network_invocations
    
    # Uniqueness: category saturation multiplier
    skills_in_category = count_skills_in_category(miner.skill.category)
    if skills_in_category == 1:
        uniqueness = 3.0  # First in category
    elif skills_in_category <= 3:
        uniqueness = 2.0
    elif skills_in_category <= 5:
        uniqueness = 1.5
    else:
        uniqueness = 1.0  # Saturated
    
    # Weighted combination
    weight = (
        0.80 * usage_score +
        0.20 * (uniqueness / 3.0)  # Normalize to 0-1
    )
    
    return weight
```

### Evaluation Cadence

- **Continuous:** Monitor invocation logs from platform API (usage counts)
- **Per-epoch:** Calculate weights from usage volume and category saturation
- **Per-epoch:** Submit weights to chain
- **Ongoing:** Analyze patterns for fake usage, spam, and fraud

### Validator Incentive Alignment

Validators do independent verification on each skill:

**Quality checks:**
- Call skills directly with test inputs
- Verify output matches declared schema
- Check response times are within timeout

**Fraud detection:**
- Analyze invocation patterns for fake usage (single caller, uniform timing, self-payment loops)
- Flag spam/duplicate skills
- Cross-reference usage diversity

**Weight calculation:**
- Pull invocation counts from agentic.ai API
- Apply fraud discounts to flagged skills
- Calculate weights (80% usage, 20% uniqueness)
- Submit to chain

**Enforcement:**
- Skills flagged by validator consensus receive zero weight
- Three violations = permanent ban
- Slashing decisions evaluated case-by-case for bad behavior or broken skills

Validators who do thorough checks and agree with consensus earn dividends. Lazy or dishonest validators get penalized as outliers.

---
