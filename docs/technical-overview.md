# Technical Overview

Last edited: 2026-07-16 12:57:59 GMT+8

## Product Contract

OpenSatia is a first-roll cart recommender with trust, safety, evidence, and
action boundaries. Given a local user profile, current meal context, and
provider-shaped menu data, it returns three distinct cart options that are easy
to compare and act on.

The target output for each cart includes:

- provider and restaurant identity
- exact menu items and selected modifiers
- item images or an honest missing-image state
- food subtotal, fees when known, and total-price confidence
- estimated calories, protein, carbohydrates, fat, and other available signals
- nutrition confidence and evidence labels
- fit across `health`, `budget`, `time`, `experience`, and `taste`
- eligibility, warnings, and provider-draft impact

## First-Roll Loop

```text
local profile + meal context + menu fixtures
                    |
          candidate generation
                    |
     hard eligibility and safety filters
                    |
        five-axis item/cart scoring
                    |
             cart mixing
                    |
       evidence and explanation layer
                    |
       select / correct / reroll
                    |
          provider-draft preview
```

The user should see three meaningfully different carts, not cosmetic variants.
The system may ask one concise question when it materially improves the carts.
When evidence is thin, OpenSatia becomes more honest, not more confident.

## Gateway Shape

The local Gateway is the stable center. It owns local state, recommendation
orchestration, evidence, approval boundaries, event traces, and provider
capability routing. Visual clients, Codex, terminal tools, and provider
connectors are replaceable adapters around it.

The initial implementation may use a compact local interface, but the behavior
must remain neutral enough for a visual web client, CLI, and agent adapter to
exercise the same recommendation loop.

## Provider Capability Boundary

Provider adapters expose narrow capabilities such as menu lookup, item detail,
modifier discovery, cart-draft preview, and manual handoff. A capability must
declare what it can observe or prepare and fail closed when state is uncertain.

Uber Eats is the primary implementation path; DoorDash proves that the contract
is not provider-specific. Synthetic or rights-cleared fixtures remain the
deterministic baseline while live paths are developed and compared.

## Safety And Evidence

- Allergies, dietary restrictions, and absolute avoids are eligibility rules,
  not soft ranking preferences.
- OpenSatia-added cart lines must remain distinguishable from existing or
  unknown provider items.
- The initial build stops before final order confirmation and payment.
- Nutrition and ingredient estimates must identify whether they come from a
  provider claim, official label, model inference, or user report.
- Images must identify their source and whether they depict the exact item.
- Restricted provider observations remain local and are not reusable public
  data by default.

## Evaluation Targets

The first evaluation set should inspect raw recommendation traces and test:

- first-roll cart validity and meaningful distinctness
- complete blocking of known allergens and absolute avoids
- arithmetic consistency for totals and nutrition summaries
- honest uncertainty and provenance labels
- image-source and generated-image truthfulness
- reroll or correction changing the requested recommendation dimension
- deterministic startup and graceful failure without live provider access
- end-to-end latency and model cost for the visible user loop
- inability to cross the final-order or payment boundary

Use deterministic checks wherever possible. Use narrowly scoped, validated
human or model judgments only where product quality is genuinely subjective.
