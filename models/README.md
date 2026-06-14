# Model collections

Named model collections for NOPE Evals blueprints. Reference one in a blueprint's `models:` list
(e.g. `models: [CORE]`) and it expands to the slugs below at run time.

- **CORE.json** — the canonical roster (20 models) NOPE Evals benchmarks against. Curated for breadth
  across providers and tiers, weighted toward models real people actually converse with (consumer
  assistants + the smaller/open models that power companion apps). This is what most blueprints
  should target, and what PR-staging evaluations are limited to.
- **QUICK.json** — a 4-model subset for cheap local iteration while authoring a blueprint.

Slugs are exact OpenRouter IDs. Edit these lists to change the roster across all blueprints at once.
Cost note: a blueprint runs against every model in its collection × the judge consensus, so adding
to CORE multiplies the cost of every run.
