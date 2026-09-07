# Schema Stock

`dots` is the shared schema stock for the Bonsai ecosystem.

## Principle

Schema is accumulated first. APIs, MCP tools, CLIs, and domain repositories reuse the stock instead of redefining equivalent structures.

```text
Schema Stock
    ↓ $ref
OpenAPI
    ↓
Go / API / MCP / CLI
```

## Categories

- `common/` — identifiers, metadata, versioning, timestamps, pagination
- `data/` — canonical objects, records, events, documents
- `pattern/` — pixel grids, palettes, cells, features
- `ontology/` — domains, concepts, relations, capabilities, agents
- `workflow/` — tasks, WorkTypes, jobs, evidence
- `api/` — problems, validation, search

## Rules

1. Prefer reuse over duplication.
2. Give every reusable schema a stable ID and version.
3. Keep semantics in schemas; extensions describe representation.
4. Keep canonical data in JSON; CSV/Parquet are projections or exchange formats.
5. Domain repositories may extend schemas, but shared primitives belong here.
6. `openapi.yaml` is the API contract and should reference Schema Stock where practical.
7. MCP is an interface over the API; it must not create a parallel schema model.

## Initial stock

```text
common/id
common/metadata
common/version
common/timestamp
common/pagination

data/object
data/record
data/event
data/document

pattern/pixel-grid
pattern/palette
pattern/cell
pattern/feature

ontology/domain
ontology/concept
ontology/relation
ontology/capability
ontology/agent

workflow/task
workflow/worktype
workflow/job
workflow/evidence

api/problem
api/validation
api/search
```

New schemas should be added here when they are reusable across two or more Bonsai domains.
