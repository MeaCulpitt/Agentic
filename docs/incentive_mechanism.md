## 1. Incentive & Mechanism Design

### Overview

Agentic operates as a unified marketplace (agentic.ai) following the Chutes (SN64) architecture model. A primary validator operates all infrastructure, while child hotkey validators compete to attract skill developers by offering attractive bonus programs funded from their emissions earnings.

**Core architectural principles:**

**Single marketplace, validator competition:** One website hosts all approved skills at agentic.ai. Validators don't fragment the ecosystem by running separate infrastructure—instead they compete transparently on how they compensate miners through bonus pools and weight-setting quality.

**Primary validator self-funded infrastructure:** The primary validator operates the marketplace website, skill execution environment, registry, and database. This infrastructure is self-funded from their emissions allocation, with zero fees extracted from skill usage. This removes infrastructure as a competitive moat and keeps barriers low for skill developers.

**Child hotkey delegation model:** Additional validators delegate to the primary validator's infrastructure via child hotkeys rather than building redundant systems. They compete by offering miners attractive bonus pools funded from their own emissions, and earn based on their weight-setting accuracy and the quality of miners they attract.

**Miners choose validator partners:** Skill developers review the transparent validator marketplace showing each validator's bonus offerings, historical miner earnings, weight-setting track record, and reputation. Miners submit skills through their chosen validator, who reviews and approves them for the marketplace. Better validator terms attract better developers, creating better skills, which improves the validator's weight-setting performance and emissions.

**Direct usage payments:** When agents invoke skills on the marketplace, they pay per invocation directly via the website. One hundred percent of usage fees flow to miners—validators take no cut of these payments. This ensures value creators capture maximum value from their work.

### Emission and Reward Logic

**Subnet emission distribution:**

The subnet allocates emissions exclusively to validators and miners, with no central treasury. The primary validator self-funds all infrastructure from their emissions share.

- **65% to Validators** - Distributed between the primary validator (infrastructure operator) and child validators (weight-setters)
- **35% to Miners** - Skill developers earn based on usage volume, quality scores, and skill uniqueness

**Validator emissions structure:**

The primary validator receives approximately one-third of the validator pool as compensation for infrastructure operation. The remaining two-thirds is distributed among child validators based on their weight-setting performance. Child validators are scored on weight accuracy (consensus alignment), miner satisfaction (bonus reliability), and ecosystem contribution (quality and quantity of aligned miners).

Higher-performing validators attract better miners through generous bonus programs, which produces higher-quality skills, leading to more accurate weight-setting and increased emissions—creating a sustainable incentive loop where investment in miners yields proportional returns in emissions.

**Miner emissions formula:**

Miners earn from three sources: direct usage fees (100% of agent payments), subnet emissions (proportional to usage share, quality, and uniqueness), and validator bonuses (from monthly competitions).

Subnet emissions to miners weight heavily toward usage volume (demonstrating real agent demand), followed by validator-assigned quality scores (technical correctness and reliability), skill uniqueness (pioneering new categories), and longevity (sustained maintenance over time). This structure ensures miners cannot game emissions without providing genuine value to agents.

**Revenue flow architecture:**

When an agent invokes a skill, the payment flows directly from agent to miner wallet on-chain, with no intermediaries taking a cut. Separately, validators fund bonus pools from their own emissions and distribute them monthly to top-performing miners aligned with their validation service. This separation ensures usage value goes entirely to creators while validator competition happens through voluntary bonus investments.

The primary validator covers infrastructure costs (hosting, compute, storage, bandwidth) from their emissions allocation, typically around 20 τ per day at mature scale. This is economically sustainable because infrastructure operation positions them to earn the largest individual validator share while keeping operational costs well below emissions income.

### Incentive Alignment for Miners and Validators

**Validator investment dynamics:**

Validators face a strategic choice between maximizing short-term profit (minimal bonus spending) versus long-term emissions growth (significant miner investment). Economic analysis shows that validators investing heavily in generous bonus pools and attracting high-quality miners earn substantially more over time than validators minimizing bonus expenses.

The mechanism works through weight-setting performance. Validators with better miners produce better skills on average, leading to more accurate quality assessments and stronger consensus alignment with other validators. This accuracy directly impacts emissions allocation, where consensus-aligned validators earn premium shares while outliers face penalties.

A validator spending 10% of emissions on miner bonuses while attracting elite developers can earn 30-50% more in total emissions compared to a stingy validator hoarding 100% of emissions but attracting mediocre talent. The math favors generosity because better miners compound into better weights, which compound into higher emissions, creating an exponential advantage over linear cost savings.

**Miner quality incentives:**

Miners building high-quality skills earn dramatically more than those producing low-quality work through three reinforcing mechanisms. First, agents vote with usage—broken or unreliable skills get tried once and abandoned, while polished skills see exponential adoption through word-of-mouth and repeated use. Second, emissions formulas heavily weight usage volume, meaning quality translates directly to earnings. Third, validator bonus competitions reward top performers, where quality determines leaderboard placement.

The earnings differential between quality tiers is severe enough to prevent rational miners from cutting corners. Commodity-level skills in crowded categories might earn minimal returns, while expertly-executed skills in specialized domains command premium usage and dominate validator leaderboards. This creates natural skill hierarchies where expertise yields sustainable moats rather than temporary advantages.

**Validator switching dynamics:**

Low switching costs enforce validator discipline. If a validator fails to deliver promised bonuses, provides poor support, or sets inaccurate weights that hurt aligned miners' emissions, those miners can migrate to competing validators within 24 hours. This migration causes immediate damage: the validator loses their best talent, weight-setting accuracy drops, emissions crater, and reputation damage makes attracting replacements difficult.

The threat of exodus keeps validators honest even when short-term incentives might favor exploitation. A validator breaking promises to miners experiences cascading losses—talent flight, accuracy degradation, emissions collapse—that far exceed any temporary gains from withheld bonuses. This dynamic creates stable equilibrium where validators compete on quality of service rather than attempting to extract value from locked-in miners.

### Mechanisms to Discourage Low-Quality or Adversarial Behavior

**Fake usage detection:**

Miners attempting to inflate usage metrics through self-invocation face multiple detection layers that make such attacks economically irrational. Validators monitor on-chain invocation patterns for red flags including extreme wallet concentration (90%+ calls from single address), self-payment loops (invoking wallet matches miner wallet), temporal uniformity (calls at mechanically regular intervals), and zero diversity (only one agent using the skill).

Cross-validator consensus amplifies detection reliability. When multiple validators independently flag the same skill for suspicious patterns, the evidence becomes overwhelming. Penalties escalate from zero weight allocation (no emissions for flagged skill) to permanent miner bans and forfeiture of pending emissions. The expected value of fake usage attacks is deeply negative: small potential short-term gains versus permanent exclusion from future earnings.

**Validator collusion resistance:**

Validators attempting to collude by assigning artificially high scores to bad skills in exchange for bribes face immediate exposure through consensus mechanisms. The subnet uses median aggregation rather than mean averaging, so outlier validators cannot significantly shift final weights even by giving extreme scores. When a validator's scores deviate substantially from consensus, automated penalties reduce their emissions allocation.

Usage verification provides a secondary defense layer. Even if a colluding validator gives a fake high quality score, agents immediately reveal ground truth through usage patterns. Broken skills receive near-zero invocations regardless of validator scores, and since emissions formulas heavily weight usage volume, the fake score produces minimal benefit to the miner. The validator pays penalties for consensus deviation while the miner earns nothing, making collusion uneconomic for both parties.

**Sybil miner attacks:**

Miners creating multiple variations of identical skills to capture more emissions face diminishing returns that make the strategy economically dominated by building one excellent skill. Emissions allocation weights usage volume heavily, so spreading 1,000 monthly invocations across 100 duplicate skills yields far less than concentrating those invocations in a single polished offering.

The uniqueness multiplier further penalizes duplicates. First-in-category skills receive 3x weight multipliers, while the hundredth variation of an HTTP client receives 1x weight with additional penalties for obvious duplication. Combined with usage concentration (agents prefer one reliable skill over many mediocre ones), Sybil strategies earn a small fraction of what focused quality development produces.

**Primary validator monopoly safeguards:**

Concerns about primary validator censorship (rejecting competitor skills to favor their own) are addressed through governance mechanisms and low validator barriers. If censorship is detected, miners can appeal to subnet governance through on-chain proposals with verifiable evidence. Successful appeals trigger governance actions including forced skill acceptance, primary validator replacement elections, or enabling multi-primary architecture for redundancy.

Economic pressure amplifies governance tools. If a primary validator develops a reputation for censorship, child validators can coordinate to support an alternative primary validator and redirect infrastructure delegation. This causes the bad actor to lose delegation, emissions, and market position. The threat of coordinated abandonment keeps primary validators honest even before governance intervention becomes necessary.

### How This Design Qualifies as Proof of Intelligence

**Intelligence validation through market mechanisms:**

Traditional proof systems validate computational work or capital commitment, but Agentic validates cognitive output through direct market testing. Intelligence is proven not through self-reported metrics or artificial benchmarks, but through agents voting with real economic value on which skills solve their problems effectively.

This approach is uniquely resistant to gaming because value creation cannot be faked. An AI could generate plausible-looking code, but if that code doesn't reliably solve agent problems, usage crashes to zero regardless of how sophisticated it appears. Conversely, a skill that consistently delivers value sees exponential adoption as agents discover, use, and recommend it to other agents.

**Technical problem-solving requirements:**

Building functional skills requires genuine understanding of complex technical domains. An OAuth2 authentication skill demands comprehension of multi-page RFC specifications, token refresh mechanisms, security flows, provider-specific implementations, and error handling patterns. A medical records integration requires years of healthcare IT experience, HIPAA compliance knowledge, HL7 FHIR standard mastery, and EHR vendor relationship navigation.

These barriers cannot be overcome through superficial effort or template copying. Agents immediately detect broken implementations through failed invocations and error responses, abandoning unreliable skills permanently. Only miners with genuine domain expertise can build skills that work reliably enough to generate sustained usage and revenue.

**Continuous adaptation and learning:**

Intelligence is demonstrated not just through initial creation but through ongoing skill maintenance and improvement. As APIs evolve, security standards change, and agent requirements shift, miners must continuously adapt their skills to maintain functionality and competitiveness.

Skills that degrade over time see usage decline and emissions drop, while skills that improve through version updates capture growing market share. This creates selection pressure for continuous learning—miners who can quickly adapt to breaking API changes, proactively optimize performance, and expand feature sets earn dramatic advantages over those who build once and abandon.

**Natural intelligence hierarchies:**

The marketplace naturally stratifies into intelligence tiers based on skill complexity and expertise requirements. Commodity skills requiring basic programming knowledge face intense competition and thin margins. Specialized skills requiring API expertise and domain knowledge command better returns with moderate competition. Expert skills requiring rare certifications, regulatory knowledge, or years of specialized experience earn premium pricing with minimal competition.

This stratification proves the system rewards intelligence proportionally. Expert-tier skills can earn 40-60x more than commodity skills because they require 40-60x more intelligence to build. The earnings gap cannot be bridged through effort alone—it requires genuine expertise that takes years to develop, creating sustainable economic moats around intelligence.

**Unfakeable value creation:**

The critical property making Agentic genuine proof of intelligence is that value creation cannot be simulated. In academic benchmarks, clever gaming strategies can achieve high scores without real understanding. In Agentic, the only path to sustainable revenue is building skills that reliably solve agent problems.

Agents have skin in the game—they pay per invocation and quickly abandon broken skills to minimize wasted funds. This economic pressure creates brutally honest feedback loops where only genuinely intelligent solutions survive. The market validates intelligence through willingness to pay, making Agentic's proof mechanism more robust than any synthetic benchmark.

### High-Level Algorithm: Task Assignment, Submission, Validation, Scoring, and Reward Allocation

**Phase 1: Skill submission and automated review**

Miners develop skills locally as containerized code packages with tests, documentation, and dependency specifications. Once complete, they submit to the primary validator's review system through an authenticated API endpoint. Submission includes the skill code, Dockerfile for execution environment, test suite, documentation, and metadata specifying category, pricing, and miner identity.

The primary validator runs automated testing pipelines covering functional correctness, security scanning, performance benchmarking, and documentation quality. Functional tests execute the miner's test suite plus validator-generated edge cases. Security scans check for vulnerabilities, hardcoded secrets, and malicious patterns. Performance tests measure latency percentiles under load. Documentation quality is assessed for completeness and clarity.

Results are aggregated into a composite quality score. Skills scoring above the approval threshold are deployed to the marketplace and made available to agents. Rejected skills receive detailed feedback identifying specific failures, allowing miners to fix issues and resubmit. This automated pipeline enables rapid iteration while maintaining quality standards.

**Phase 2: Validator weight-setting through consensus**

Child validators continuously sample random skills from the marketplace and run independent quality assessments. Each validator invokes skills with test inputs, measures response accuracy and latency, checks uptime reliability, and analyzes usage patterns for legitimacy indicators.

Validators assign weight scores to each miner based on their skill portfolio's aggregate quality. These weights are submitted to the subnet chain every epoch alongside the validator's version key. The chain aggregates weights from all validators using median rather than mean calculation, making the system robust to outlier manipulation.

Validators whose weights significantly deviate from consensus face automatic emissions penalties. This creates strong incentives for honest, accurate weight-setting while preventing collusion or bribery attacks. The median aggregation ensures no single validator can meaningfully distort the final weight distribution.

**Phase 3: Agent discovery and skill invocation**

Agents browse the marketplace through search and category navigation, viewing skills ranked by quality scores, usage volume, pricing, and performance metrics. Once an agent identifies a needed skill, they invoke it by sending an authenticated API request to the primary validator's execution infrastructure with invocation parameters and payment.

The primary validator loads the skill's Docker container, injects agent-provided environment variables and parameters, executes the skill with timeout protection, and returns results. Payment is settled on-chain directly from agent wallet to miner wallet, with the primary validator simply facilitating the transaction without taking a cut.

This architecture allows agents to invoke any skill seamlessly while ensuring miners receive immediate payment for usage. The primary validator's role is purely operational—providing reliable execution infrastructure—with no ability to intercept or redirect payments.

**Phase 4: Ongoing quality monitoring and pattern detection**

Validators continuously monitor live skills through random health checks, invoking them with test cases and verifying correct responses. Skills failing health checks are temporarily delisted and miners are notified to investigate. Persistent failures result in permanent weight reductions.

Usage pattern analysis runs alongside health checks, examining invocation distributions for fake usage indicators. High wallet concentration, self-payment loops, mechanical timing patterns, or geographic anomalies trigger fraud investigations. When multiple validators independently flag the same skill, evidence is shared and consensus penalties are applied including weight zeroing and potential permanent bans.

This continuous monitoring creates an always-on quality assurance system that catches degradation, detects gaming, and maintains marketplace integrity without requiring manual intervention.

**Phase 5: Emissions distribution through chain consensus**

Each epoch, the subnet chain calculates emissions distribution based on aggregated validator weights and on-chain usage data. Validator emissions are allocated based on weight-setting accuracy (consensus alignment), miner satisfaction (bonus payout reliability measured through miner retention), and ecosystem contribution (number and quality of aligned miners).

Miner emissions are calculated from usage volume (share of total network invocations), validator quality scores (median weight from all validators), skill uniqueness (pioneering new categories versus commodity skills), and longevity bonuses (sustained maintenance over six-plus months). These emissions are distributed directly to miner wallets each epoch.

The primary validator receives their infrastructure allocation as a fixed percentage of validator emissions, ensuring sustainable funding for marketplace operation without usage fee extraction.

**Phase 6: Validator bonus competitions and distributions**

Validators run monthly leaderboard competitions for miners aligned with their validation service. Rankings are determined by composite scores weighing usage volume, quality ratings, agent satisfaction, and documentation quality. Top performers receive bonus payments from the validator's emissions allocation.

These bonuses are funded entirely from validator earnings and paid directly from validator wallets to miner wallets at month's end. The size and structure of bonus programs varies by validator, with each competing to offer the most attractive terms to recruit and retain top mining talent.

Bonus distribution is transparent and auditable, allowing miners to verify promised payments were delivered. Validators who fail to pay announced bonuses face immediate reputation damage and miner exodus, enforcing accountability through market discipline.

**Algorithm properties and guarantees:**

The complete system implements decentralized quality control through consensus weight-setting where no single validator controls outcomes. Market-driven validation ensures miners cannot earn without providing real value since agent usage determines success. Self-correcting mechanisms detect and penalize bad validators through outlier analysis. Incentive alignment creates sustainable economics where validators profit by attracting quality miners rather than extracting value. Complete transparency via on-chain weights, scores, and payments enables public auditability and trust.

---
