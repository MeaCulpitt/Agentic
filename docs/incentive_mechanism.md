## Incentive & Mechanism Design

### Emission and Reward Logic

Miners earn from two sources:

1. **Usage payments:** Agents pay per skill invocation via agentic.ai. Platform takes 5% fee; 95% goes to miner.

2. **Subnet emissions:** Distributed to Top 50 miners based on market share.

**Weight formula:**
```
miner_weight = number_of_agent_downloads (100%)
```

**Distribution:**
- Top 50 miners earn emissions
- Each miner's share = their downloads / total downloads of Top 50
- Bottom miners excluded from emissions (no payout)

*Note: The Top 50 threshold may increase as miner volume grows.*

### Incentive Alignment for Miners and Validators

**Miners** maximize earnings by:
- Building skills agents actually download
- Keeping skills working (broken skills get abandoned)

**Validators** maximize earnings by:
- Accurate weight-setting aligned with consensus
- Detecting fraud and fake download activity
- Maintaining uptime

### Mechanisms to Discourage Low-Quality or Adversarial Behavior

**Stake requirement:**
- 0.1 τ per skill (slashed for fraud)

**Fraud detection:**
Validators analyze download patterns for:
- **IP concentration** — multiple downloads from same IP address
- **Wallet concentration** — same wallet downloading same skill repeatedly
- **Temporal patterns** — suspiciously coordinated download activity
- **Rate limiting** — one download per agent per skill version (re-download allowed on skill update)

Skills flagged by validator consensus receive zero weight. Three violations result in a permanent ban. Slashed stakes are burned.

### Proof of Effort / Proof of Intelligence

This subnet qualifies as proof of effort:

**Skill development effort:** Building functional skills requires genuine expertise — OAuth2 skills demand RFC comprehension; medical integrations require HIPAA knowledge.

**Continuous maintenance:** Skills degrade as APIs evolve. Miners must update when dependencies change or usage drops.

**Market validation:** Agents vote with real economic value. They download skills they need and abandon broken ones quickly. Only genuinely useful skills gain traction.
