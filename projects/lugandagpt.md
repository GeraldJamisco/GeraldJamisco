# LugandaGPT: research toward a Luganda language model

**Status: early-stage research. No model has been trained yet.** I say this first because it is true, and because
the work so far is the careful groundwork that a language model needs.

**Stack:** Python · pytest · web app for native-speaker translation and review

## What exists
- A written mission, roadmap and decision log, with gates that must pass before any training spend.
- A **benchmark specification** for Luganda conversation quality (approved, no items written yet).
- **Translation Studio**: a local web app for native speakers to translate and review training examples.
- **Sunbird API client**, unit-tested, used to measure an existing Luganda model as a baseline.
- Data-governance rules, source validation tooling, a Python test suite.

## What I learned
Low-resource language work is mostly data and evaluation, not model code. Deciding how you will measure quality,
and who reviews the data, comes before choosing an architecture.

<!-- TODO before publishing: keep the status line at the top. Remove tracked zip files from the repo first
(deployment/releases/*.zip). Push the 11 local commits only after reviewing them. -->
