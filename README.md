# OpenSatia

Last edited: 2026-07-16 12:57:59 GMT+8

**Decode your cravings. Bomb food every time.**

OpenSatia is a local-first, food-first system that helps an AI agent turn a
user's context into three safe, honest, visually compelling cart options.
Food delivery is the first wedge. The durable center is an OpenSatia Gateway,
not a particular model, browser, provider, or user interface.

## First Build

The first runnable slice is deliberately narrow:

1. Load a local sample profile, meal context, and provider-shaped menu data.
2. Treat allergies, dietary restrictions, and absolute avoids as hard filters.
3. Ask at most one high-value question when it materially changes the result.
4. Produce three distinct cart options with images, price, estimated nutrition,
   confidence, evidence labels, and five-axis fit.
5. Let the user select, correct, or reroll with minimal interaction.
6. Preview a provider handoff without placing an order or submitting payment.

OpenSatia optimizes for first-roll satisfaction and successful food action, not
scrolling, engagement, or time spent.

## Five Axes

Every cart can be evaluated through five stable dimensions:

- `health`
- `budget`
- `time`
- `experience`
- `taste`

Scores must be backed by observed or inferred data and accompanied by honest
confidence and provenance. They are not substitutes for allergy checks or
medical advice.

## Provider Direction

- **Uber Eats** is the primary provider path and will be validated from Taiwan.
  OpenSatia will compare an official API-ready adapter with an experimental
  custom connector behind the same capability boundary.
- **DoorDash** is the secondary US-market demonstration. It should prove that
  the same cart contract can drive another provider without requiring feature
  parity.

The judged and development paths remain runnable from synthetic or
rights-cleared local fixtures. Live provider availability must not determine
whether OpenSatia starts or produces recommendations.

## Safety Boundary

The first version may read data, create local drafts, and preview a provider
draft. It must not place an order, submit payment, clear a cart, bypass an
account challenge, or present uncertain nutrition as provider-confirmed fact.

Provider captures, session data, personal histories, addresses, and credentials
must never be committed to this repository.

## Architecture

```text
visual client / agent / CLI
            |
      OpenSatia Gateway
            |
 candidate generation -> eligibility -> scoring -> cart mixing -> evidence
            |
   provider capability adapters
```

See [Technical Overview](docs/technical-overview.md) for the current build
contract and evaluation targets.

## Development Status

OpenSatia is under active construction. This curated root establishes the
public product and safety boundary before the runnable application lands.
Setup and run commands will be added with the first executable app-shell commit
rather than documented speculatively.

The current build is being accelerated during OpenAI Build Week, but OpenSatia
is designed as a continuing product and protocol project rather than an
event-specific demo.

## License

OpenSatia code is licensed under the [MIT License](LICENSE). That license does
not grant rights to third-party provider data, menu content, images,
trademarks, or authenticated captures.
