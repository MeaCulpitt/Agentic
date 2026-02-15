## Incentive & Mechanism Design

### Overview

The subnet owner operates agentic.ai—the marketplace website, skill registry, and execution infrastructure. Miners develop skills and submit them to the marketplace. Validators run automated tests against skills and set weights based on quality and usage. Agents pay per invocation, with payments flowing directly to miners.

### Emission and Reward Logic

Miners earn from two sources:

**1. Usage payments:** Agents pay per skill invocation via agentic.ai. The platform takes a 5% fee to cover infrastructure costs; 95% goes to the miner.

**2. Subnet emissions:** Distributed via Yuma Consensus based on validator weights. Validators set weights according to:

```
miner_weight = usage_volume × uniqueness_multiplier
```

Where:
- **usage_volume** (80% weight): Share of total network invocations. Demonstrates real agent demand. Agents pay per call—they only keep using skills that work.
- **uniqueness_multiplier** (20% weight): Based on category saturation. First skill in a category = 3x, 2-3 skills = 2x, 4-5 skills = 1.5x, 6+ skills = 1x. Categories are platform-defined.

Validators earn standard Bittensor dividends for accurate weight-setting.

### Incentive Alignment for Miners and Validators

**Miners** maximize earnings by:
- Building skills agents actually use (usage drives both payments and emissions)
- Targeting underserved categories (uniqueness multiplier)
- Keeping skills working (broken skills don't get used)

**Validators** maximize earnings by:
- Running accurate quality assessments (consensus alignment)
- Detecting fake usage (outlier validators face penalties)
- Maintaining uptime (active validators earn more)

The alignment is simple: miners earn when agents pay, validators earn when weights are accurate.

### Mechanisms to Discourage Low-Quality or Adversarial Behavior

**Fake usage detection:**
Validators analyze on-chain invocation patterns for:
- Wallet concentration (>90% calls from single address)
- Self-payment loops (invoker wallet = miner wallet)
- Temporal uniformity (mechanically regular intervals)
- Zero diversity (single agent using skill)

Skills flagged by validator consensus receive zero weight. Three violations result in a permanent ban.

**Quality enforcement:**
- Stake requirement: Miners stake 0.05 τ per skill
- Slashing: Evaluated case-by-case by validators. Stake lost for skills that don't work and/or confirmed bad behavior. Cost of entry, cost of failure
- Delisting: Reserved for bad actors — fake usage, sybil attacks, malicious behavior
- Slashed stakes are burned (deflationary)

The market handles quality naturally: broken skills don't get used, so miners don't earn. 

**Sybil & spam resistance:**
- Stake requirement (0.05 τ per skill) creates economic friction
- Miners must verify their skill doesn't already exist on the marketplace before submitting
- Duplicate or near-duplicate skills = stake slashed
- Validators flag spam, consensus confirms, stake burned
- Uniqueness multiplier rewards novel skills (first in category = 3x)

### Proof of Effort / Proof of Intelligence

This subnet qualifies as proof of effort through verifiable work at multiple levels:

**Skill development effort:**
Building functional skills requires genuine expertise. An OAuth2 skill demands RFC comprehension, token refresh logic, provider-specific implementations. A medical records integration requires HIPAA knowledge, HL7 FHIR mastery, EHR vendor relationships. This expertise cannot be faked—broken skills fail tests and get abandoned by agents.

**Continuous maintenance effort:**
Skills degrade as APIs evolve. Miners must push updates when dependencies change, security vulnerabilities emerge, or agent requirements shift. Abandoned skills see usage decline and emissions drop.

**Market validation:**
Agents vote with real economic value. They pay per invocation and quickly abandon broken skills. This creates unfakeable feedback loops—only genuinely useful skills generate sustained revenue.

**Verifiable outputs:**
- Every invocation logged on-chain
- Test results publicly auditable
- Usage statistics transparent
- Quality scores derived from deterministic tests

### High-Level Algorithm

**1. Skill Submission**
- Miner develops skill locally (code + Dockerfile + tests + docs)
- Miner stakes 0.05 τ and submits to agentic.ai via authenticated API
- Platform runs automated smoke tests (functional, security)
- Skills passing threshold deployed to marketplace

**Skill Updates:**
- Miners can push updates to live skills
- Updates reset success rate tracking (prevents gaming via version churn)
- Stake remains locked until miner voluntarily delists the skill

**2. Discovery & Invocation**
- Agent searches marketplace by category/capability
- Agent invokes skill via agentic.ai API with parameters + payment
- Platform executes skill in sandboxed container
- Results returned; 95% of payment settled to miner, 5% retained by platform

**3. Validation & Scoring**
- Validators sample random skills each epoch
- Run independent quality assessments (invoke with test inputs, measure accuracy/latency)
- Check uptime, analyze usage patterns for fraud
- Assign weight scores based on formula

**4. Weight Submission**
- Validators submit weights to chain each epoch
- Chain aggregates via Yuma Consensus (median)
- Outlier validators face emissions penalties

**5. Reward Distribution**
- Miner emissions distributed based on aggregated weights
- Validator emissions distributed based on consensus alignment
- Usage payments settled per-invocation (95% miner, 5% platform)
