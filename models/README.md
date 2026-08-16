# Model collections

Named model collections for NOPE Evals blueprints. Reference one in a blueprint's `models:` list
(e.g. `models: [CORE]`) and it expands to the slugs below at run time.

- **CORE.json** — the canonical roster (28 models) NOPE Evals benchmarks against. Curated for breadth
  across providers and tiers, weighted toward models real people actually converse with (consumer
  assistants + the smaller/open models that power companion apps). This is what most blueprints
  should target, and what PR-staging evaluations are limited to.

  > **One arm is NOPE-operated.** `nope:invar-0.1` is NOPE's own conversational model and is
  > benchmarked here under the same blueprints, judges, coverage gate and safety floor as every
  > other subject. It resolves against a NOPE endpoint, so cloning this repo and running CORE
  > elsewhere will fail on that one arm; drop it to run the other 27. No NOPE model is ever used
  > as a judge.

- **LEAN.json** — an 11-model mid-size roster (one current model per major provider, all 2025–2026,
  cheap-to-mid tier — no flagships like Opus/GPT-5/o3). ~7× cheaper to run than CORE. Use this for
  expensive blueprints (long multi-turn, multi-temperature sweeps) where the full CORE roster is
  cost-prohibitive, and when you want a current, diverse cross-section without stale 2024 models.
- **FRONTIER.json** — a 12-model flagship roster (the current flagship from each major lab,
  2026 generation: opus-5, fable-5, sonnet-5, gpt-5.6-sol, gpt-5.5, gemini-3.1-pro, grok-4.5,
  kimi-k3, glm-5.2, deepseek-v4-pro, qwen3.7-max, mistral-large-2512). Expensive — use only for
  deliberate frontier-tier probes with firm theories to test, never for routine runs.
- **QUICK.json** — a 4-model subset for cheap local iteration while authoring a blueprint.

Slugs are exact OpenRouter IDs. Edit these lists to change the roster across all blueprints at once.
Cost note: a blueprint runs against every model in its collection × the judge consensus, so adding
to CORE multiplies the cost of every run.
