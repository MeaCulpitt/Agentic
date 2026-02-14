## 2. Miner Design

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

**Usage (70%):** Share of total network invocations. Agents pay per call — sustained usage proves the skill works.

**Success Rate (20%):** Percentage of invocations completing without errors. Skills below 80% after 100+ calls are delisted.

**Uniqueness (10%):** Category novelty. First skill in a category earns 3x multiplier; saturated categories earn 1x.
