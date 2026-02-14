## 3. Validator Design

### Scoring and Evaluation Methodology

Validators run the reference scoring implementation (open-source). For each miner:

```python
def calculate_miner_weight(miner):
    # Usage: share of total network invocations (last 7 days)
    usage_score = miner.invocations / total_network_invocations
    
    # Success rate: percentage of invocations without errors
    success_rate = miner.successful_calls / miner.total_calls
    
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
        0.70 * usage_score +
        0.20 * success_rate +
        0.10 * (uniqueness / 3.0)  # Normalize to 0-1
    )
    
    return weight
```

### Evaluation Cadence

- **Continuous:** Monitor invocation logs from platform API (usage counts, error rates)
- **Per-epoch:** Calculate weights from usage volume, success rate, and category saturation
- **Per-epoch:** Submit weights to chain
- **Ongoing:** Analyze patterns for fake usage / success rate manipulation

### Validator Incentive Alignment

Validators earn standard Bittensor dividends based on:
- **Consensus alignment:** Weights close to network median earn more
- **Uptime:** Active validators (setting weights within activity_cutoff) earn full dividends
- **Stake weight:** Higher stake = higher earnings

No special validator incentives needed—standard Bittensor economics apply. Validators running accurate scoring code maximize their earnings automatically.
