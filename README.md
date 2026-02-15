# Agentic - the decentralized marketplace for AI agent skills

---

## What is Agentic?

Agentic is a Bittensor subnet where AI agents discover, invoke, and pay for executable skills. Miners build skills (browser automation, document processing, search, communication tools). Validators verify quality. Agents pay per use.

**Think of it as an app store for AI agent capabilities — decentralized, permissionless, and revenue-generating for developers.**

---

## How It Works

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Miners    │────▶│  agentic.ai │◀────│   Agents    │
│ (build      │     │ (marketplace│     │ (discover & │
│  skills)    │     │  & execution)│     │  invoke)    │
└─────────────┘     └─────────────┘     └─────────────┘
                           │
                    ┌──────┴──────┐
                    │ Validators  │
                    │ (verify     │
                    │  quality)   │
                    └─────────────┘
```

1. **Miners** build containerized skills (code + Docker + tests)
2. **Miners** stake 0.05 τ and submit to the marketplace
3. **Validators** verify skills work and detect fraud
4. **Agents** search, invoke, and pay per call (95% to miner, 5% platform)
5. **Emissions** distributed based on usage × uniqueness

---

## Key Features

- **Usage-based rewards** — Skills that agents actually use earn more
- **Market-driven quality** — Broken skills don't get used, so miners don't earn
- **Uniqueness incentives** — First skill in a category earns 3x multiplier
- **No lock-in** — Standard API, switch skills freely
- **Fraud protection** — Validators detect fake usage, spam gets slashed

---

## Weight Formula

```python
miner_weight = (
    0.80 * usage_volume +      # Share of total invocations
    0.20 * uniqueness          # Category saturation multiplier
)
```

Usage drives rewards. Build skills agents actually use → earn more.

---

## Competition & Quality

Multiple skills can exist per category, ranked by usage. Bottom 10% eliminated every 2 weeks — stake slashed.

**Validators check:**
- Skills respond within timeout
- Output matches declared schema
- No fake usage patterns

**Slashing for:**
- Bottom 10% each cycle
- Broken skills
- Fraud/spam

**Permanent ban:** Three violations.

The market handles quality naturally: broken skills don't get used → miners don't earn → they get eliminated.

---

## Skill Categories

Skills span any capability agents need:

- **Browser automation** — Form filling, scraping, screenshots
- **Search & research** — Web search, document lookup, data aggregation
- **Communication** — Email, Slack, Discord, SMS
- **Document processing** — PDF extraction, OCR, summarization
- **And more** — Any containerized capability an agent can invoke

---

## For Miners

Build skills, earn TAO + usage payments.

```bash
# Skill package structure
my-skill/
├── skill.json      # Metadata, pricing, schemas
├── Dockerfile      # Execution environment
├── src/            # Implementation
├── tests/          # Test suite
└── README.md       # Documentation
```

**Earnings:**
- 95% of every invocation payment
- Subnet emissions based on weight
- 3x uniqueness bonus for pioneering categories

**Requirements:**
- Stake 0.05 τ per skill
- Pass platform smoke tests
- Compete: bottom 10% eliminated every 2 weeks

---

## For Validators

Run the reference implementation, earn dividends.

```bash
# Clone and run validator
git clone https://github.com/agentic-ai/agentic-subnet
cd agentic-subnet
pip install -r requirements.txt
python neurons/validator.py --wallet.name <your_wallet> --netuid <TBD>
```

Validators:
- Call skills directly to verify they work
- Detect fake usage, spam, and fraud
- Calculate weights from usage and uniqueness
- Submit weights to chain each epoch

---

## For Agents

Invoke skills via simple API.

```bash
curl -X POST https://api.agentic.ai/invoke \
  -H "Authorization: Bearer <your_api_key>" \
  -d '{
    "skill_id": "web-scraper-v2",
    "parameters": {"url": "https://example.com"},
    "payment": "0.001"
  }'
```

Response:
```json
{
  "result": {"title": "Example Domain", "content": "..."},
  "execution_time_ms": 1250,
  "cost_charged": "0.001"
}
```

---

## Roadmap

| Phase | Timeline | Milestones |
|-------|----------|------------|
| **Testnet** | Week 1-4 | 5-10 reference skills, 3-5 validators, OpenClaw integration |
| **Soft Launch** | Week 5-8 | Mainnet, invite-only miners, 20-30 skills |
| **Public Launch** | Week 9+ | Open registration, marketing push |

---

## Links

- **Website:** [agentic.ai](https://agentic.ai) *(coming soon)*
- **Docs:** [docs.agentic.ai](https://docs.agentic.ai) *(coming soon)*
- **Discord:** [Join](https://discord.gg/agentic) *(coming soon)*
- **Twitter:** [@agentic_ai](https://twitter.com/agentic_ai) *(coming soon)*

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---
