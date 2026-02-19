# Agentic - the decentralized marketplace for AI agent skills

---

## What is Agentic?

Agentic is a Bittensor subnet where AI agents discover and download executable skills. Miners build skills (browser automation, document processing, search, communication tools). Validators detect fraud. Agents pay to download.

**Think of it as an app store for AI agent capabilities — decentralized, permissionless, and revenue-generating for developers.**

---

## How It Works

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Miners    │────▶│  agentic.ai │◀────│   Agents    │
│ (build      │     │ (marketplace│     │ (discover & │
│  skills)    │     │  & download)│     │  download)  │
└─────────────┘     └─────────────┘     └─────────────┘
                           │
                    ┌──────┴──────┐
                    │ Validators  │
                    │ (detect     │
                    │  fraud)     │
                    └─────────────┘
```

1. **Miners** build containerized skills (code + Docker + tests)
2. **Miners** submit skills to the marketplace
3. **Validators** detect fraudulent download activity
4. **Agents** search and download skills (95% to miner, 5% platform)
5. **Emissions** distributed to Top 50 miners based on downloads

---

## Key Features

- **Download-based rewards** — Skills that agents actually download earn emissions
- **Market-driven quality** — Broken skills don't get downloaded, so miners don't earn
- **Top 50 earners** — Only top 50 miners by downloads receive emissions
- **No lock-in** — Standard API, switch skills freely
- **Fraud protection** — Validators detect fake downloads

---

## Weight Formula

```python
miner_weight = miner's_downloads / total_downloads_of_top_50
```

Top 50 miners earn emissions proportional to their market share. The threshold may increase as miner volume grows.

---

## Competition & Quality

Multiple skills exist per category, ranked by downloads. The market handles quality naturally: broken skills don't get downloaded → miners don't earn → they fade away.

---

## Fraud Detection

Validators analyze download patterns for:
- **IP concentration** — multiple downloads from same IP
- **Wallet concentration** — same wallet downloading same skill repeatedly
- **Temporal patterns** — suspiciously coordinated download activity
- **Rate limiting** — one download per agent per skill version

Miners flagged for fraudulent activity receive zero weight.

---

## For Miners

Build skills, earn TAO + download payments.

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
- 99% of every download payment
- Subnet emissions (Top 50 miners by downloads)

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
- Detect fake download activity (IP, wallet, patterns)
- Calculate weights from download counts
- Submit weights to chain each epoch

---

## For Agents

Download skills via simple API.

```bash
curl -X POST https://api.agentic.ai/download \
  -H "Authorization: Bearer <your_api_key>" \
  -d '{
    "skill_id": "web-scraper-v2",
    "payment": "0.001"
  }'
```

Response:
```json
{
  "skill_package": {...},
  "download_confirmed": true,
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
