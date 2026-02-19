## Incentive & Mechanism Design

### Emission and Reward Logic

Miners earn from two sources:

1. **Usage payments:** Agents pay to download skills via Agentic website. Platform takes 1% fee; 99% goes to miner.

2. **Subnet emissions:** Distributed to Top 50 miners based on market share.

**Weight formula:**
```
miner_weight = miner's_downloads / total_downloads_of_top_50
```

**Distribution:**
- Top 50 miners earn emissions
- Each miner's share is proportional to their downloads
- Bottom miners excluded from emissions (no payout)

*Note: The Top 50 threshold may increase as miner volume grows.*

### Incentive Alignment for Miners and Validators

**Miners** maximize earnings by:
- Building skills agents actually download
- Keeping skills working (broken skills get abandoned)
- Updating skills

**Validators** maximize earnings by:
- Accurate weight-setting aligned with consensus
- Detecting fraud and fake download activity
- Maintaining uptime

### Mechanisms to Discourage Low-Quality or Adversarial Behavior

**Fraud detection:**
Validators analyze download patterns for:
- **IP concentration** — multiple downloads from same IP address
- **Wallet concentration** — same wallet downloading same skill repeatedly
- **Temporal patterns** — suspiciously coordinated download activity
- **Rate limiting** — one download per agent per skill version (re-download allowed on skill update)

Miners flagged for fraudulent activity receive zero weight.

### Proof of Effort / Proof of Intelligence

This subnet qualifies as proof of effort:

**Skill development effort:** Building functional skills requires genuine expertise in a particular domain area.

**Market validation:** Agents vote with real economic value. They download skills they need and abandon broken ones quickly. Only genuinely useful skills gain traction.

---

Continue with **Miner Design**?
