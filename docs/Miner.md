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
- Or rejection with specific validation failures
```

**Skill download:**
```
Input:
- skill_id: string
- payment: TAO amount

Output:
- Skill package (Docker image, code, schemas)
- Confirmation of download
```

### Performance Dimensions

**Downloads (100%):** Number of agents who download the skill. Agents vote with their wallets — they only download skills they need. Broken skills don't get downloaded, so miners don't earn.

**Market decides:** The market handles quality naturally. Skills that don't work get abandoned. Skills that agents find useful gain downloads and rise in the rankings.
