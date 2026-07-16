# OpenSatia Public Build Guide

Last edited: 2026-07-16 13:15:15 GMT+8

This worktree maps to `https://github.com/OpenSatia/opensatia`. It is the
public-facing implementation and submission repository for OpenSatia. OpenAI
Build Week is the current execution constraint, not the product identity.

## Start Here

- Read `README.md` for the product promise and current public status.
- Read `docs/technical-overview.md` for the first-roll contract, architecture,
  safety boundary, and evaluation targets.
- Read `CONTRIBUTING.md` before preparing a public issue or pull request.
- Read `SECURITY.md` before handling a vulnerability, sensitive diagnostic, or
  provider-action safety failure.
- Keep changes centered on a runnable first-roll experience that produces
  three safe, honest cart options with minimal user effort.

## Workspace Boundaries

- Write scope: `/Users/andrewfai/Documents/OpenSatia/opensatia-protocol`.
- Canonical remote: `https://github.com/OpenSatia/opensatia`.
- Optional private context: `../opensatia-ideation-private`, when present, is
  local-only, read-only exploratory material. Never import it wholesale or
  push it through a branch, tag, release, issue, artifact, or attachment.
- Read-only reference: `../ikigai-hackathon-poc`. Do not edit or commit from it
  unless the user explicitly changes that boundary.
- Stage, commit, and push only from this repository's own Git worktree. Never
  stage the parent OpenSatia workspace.

## Active Build

- Produce three distinct first-roll cart options from local provider-shaped
  fixtures.
- Apply allergies, dietary restrictions, and absolute avoids before ranking.
- Show images, total price, nutrition estimates, confidence, evidence labels,
  and five-axis fit.
- Support select, correct, reroll, and provider-draft preview with minimal
  interaction.
- Keep the judged path deterministic even when live providers or models are
  unavailable.

## Provider Strategy

- Uber Eats is primary and must be credible from Taiwan. Compare an official
  API-ready adapter with an experimental custom connector behind one provider
  capability interface.
- DoorDash is the secondary US-market demonstration. Reuse the same cart and
  handoff contract without forcing provider parity.
- Provider adapters are replaceable capabilities. Uber Eats, DoorDash, Chrome,
  Codex, or any generated UI must not become the OpenSatia protocol.

## Hard Boundaries

- Never commit `.env` values, credentials, cookies, tokens, addresses, payment
  data, provider dumps, authenticated captures, or personal ordering history.
- Never place an order, submit payment, click final confirmation, bypass an
  account challenge, or clear a provider cart in the first version.
- Never treat a provider comment as an allergen guarantee.
- Never present inferred nutrition, ingredients, images, prices, or
  availability as provider-confirmed facts.
- Generated food images must be labeled and must not masquerade as item
  evidence.

## Working Discipline

- Prefer the smallest change that improves the first three carts or the judge's
  ability to experience them.
- Use focused, descriptive commits that represent verified progress.
- Inspect raw traces and define concrete failure modes. Do not rely on vague
  helpfulness scores or unvalidated model judges.
- Keep tests proportional, with hard checks for safety, cart validity,
  distinctness, evidence honesty, latency, and reroll behavior.
- Any edited Markdown file must contain exactly one visible `Last edited:`
  timestamp in GMT+8.
- Run `git status --short` and relevant checks before every push. Do not include
  unrelated local files.
- Keep the README product-first. Event logistics and exploratory futures do not
  belong in the public product narrative unless required for submission.
