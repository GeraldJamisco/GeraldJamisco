# Klan Fleet Demo: a fleet and trips app with ERP integration

Built in response to an IT Officer (Mobile Applications Development) vacancy, to show what I would build rather
than only describe it. All data is fake.

**Stack:** Flutter app · Node.js / Express / SQLite API · Python ERP connector
**Tests:** 12 API tests, 10 connector tests (the Flutter app's screens are not yet covered by tests)

## What it does
- Drivers: see assigned trips, move them through picked up, in transit and delivered, log fuel, report problems.
- Managers: live overview, create and assign trips, cancel trips, watch ERP sync health.
- ERP: delivered trips, fuel expenses and incidents arrive automatically in the ERP's own format.

## The interesting part
A **transactional outbox**: each business change and its ERP event are saved in one database transaction, so an
ERP outage never blocks drivers and nothing is lost. A Python connector delivers events with a mapping layer,
exponential-backoff retries, idempotency keys (duplicates are booked once) and a dead-letter limit.

## Honest notes
First Flutter project. Not built yet: offline queue, GPS, proof-of-delivery photo, push notifications, HTTPS.

<!-- TODO before publishing: add screenshots of the driver and manager screens and a 30-second screen recording. -->
