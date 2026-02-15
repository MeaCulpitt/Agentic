## Miner Design

### Miner Tasks

Miners are skill developers. They:
1. Build containerized code modules that solve specific agent problems
2. Write comprehensive test suites
3. Document API specifications and usage examples
4. Submit skills to the marketplace
5. Maintain skills as dependencies and requirements evolve

### Expected Input → Output Format

**Skill package submission:**
```
Input:
- skill.json (metadata: name, category, pricing, input/output schemas)
- Dockerfile (execution environment)
- src/ (implementation code)
- tests/ (test suite)
- README.md (documentation)

Output:
- Deployment confirmation with skill_id
- Or rejection with specific test failures
```

**Skill invocation:**
```
Input:
- skill_id: string
- parameters: JSON (skill-specific)
- env_vars: JSON (API keys, credentials)
- payment: TAO amount

Output:
- result: JSON (skill-specific output)
- execution_time_ms: number
- cost_charged: TAO amount
```

### Performance Dimensions

**Usage (80%):** Share of total network invocations. Agents pay per call — sustained usage proves the skill works.

**Uniqueness (20%):** Category novelty. First skill in a category earns 3x multiplier; saturated categories earn 1x.

The market handles quality naturally: broken skills don't get used, so miners don't earn. Validators monitor for fraud and spam — not arbitrary quality thresholds.

**Category Competition:** Multiple skills exist per category, ranked by usage. Bottom 10% eliminated every 2 weeks — stake slashed. Build something better than what exists, or get cut.

---
