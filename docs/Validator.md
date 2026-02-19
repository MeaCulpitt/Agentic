## Validator Design

### Scoring and Evaluation Methodology

Validators run the reference scoring implementation (open-source). For each miner:

```python
def calculate_miner_weight(miner):
    # Downloads: share of total downloads within Top 50
    miner_downloads = miner.total_downloads
    top_50_total = sum(m.total_downloads for m in get_top_50_miners())
    
    weight = miner_downloads / top_50_total
    
    return weight
```

### Evaluation Cadence

- **Per-epoch:** Calculate weights from download counts
- **Ongoing:** Analyze download patterns for fraud
- **Per-epoch:** Submit weights to chain

### Validator Incentive Alignment

Validators maximize earnings by:
- Accurate weight-setting aligned with consensus
- Detecting fake download activity (IP, wallet, temporal patterns)
- Maintaining uptime

Validators who agree with consensus and catch fraud earn dividends. Lazy or colluding validators face penalties as outliers.
