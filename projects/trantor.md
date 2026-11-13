# Trantor: a Python system built to fail safe

A research and paper-trading system for gold (XAUUSD). It reads market data, evaluates rules, records every
decision, and simulates trades. **It cannot send real orders**: execution is refused by design, and no strategy in
the repository is claimed to be profitable. I include it as a demonstration of engineering discipline, not of
trading results.

**Stack:** Python 3.12+ · standard-library dashboard · pytest · MetaTrader 5 (read-only data)
**Size:** 349 automated tests, operator guide, acceptance report, written strategy spec

## What it shows
- **Typed domain models and strict configuration.** Unknown or unsafe config is rejected, never defaulted.
- **A safety gate that fails closed.** Paper mode only; hard risk ceilings that config files can tighten but
  never loosen; orders require an approved risk assessment and a unique client order ID.
- **Honest data handling.** Market-data results are explicit (`ok`, `empty`, `stale`, `invalid`, `provider_error`);
  failures are never turned into trading evidence.
- **A read-only research dashboard** over 66,000+ decision records, paginated server-side.
- **Deterministic, offline tests**: no broker, network or secrets needed to run the suite.

## Relevance
The same habits matter in any system that handles money or operations: validate inputs, make failure explicit,
and make unsafe states hard to reach.

<!-- TODO before publishing: confirm no secrets in history (scan done: clean), add a screenshot of the dashboard,
and keep the "no live trading" statement at the top. -->
