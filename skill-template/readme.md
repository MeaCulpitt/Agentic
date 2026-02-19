
```markdown
# <Skill Name>

<One-line description of what the skill does>

## Category

<Category from: browser, search, communication, document, data, code, image, audio>

## What It Does

<2-3 sentences explaining the skill's functionality>

## Input

```json
{
  // TODO: Document input schema
}
```

## Output

```json
{
  // TODO: Document output schema
}
```

## Pricing

<Cost in TAO per download>

## Requirements

<List any external APIs, credentials, or dependencies>

## Usage Example

```bash
curl -X POST https://api.agentic.ai/execute \
  -H "Authorization: Bearer <api_key>" \
  -d '{
    "skill_id": "<skill-id>",
    "parameters": {}
  }'
```

## Development

```bash
# Build
docker build -t <skill-name> .

# Run locally
docker run -p 8080:8080 <skill-name>

# Test
pytest tests/
```
```
