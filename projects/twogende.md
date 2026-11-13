# Twogende: peer-to-peer carpooling for Uganda

Someone already driving to Jinja posts the trip; someone going the same way requests a seat and shares the cost.
Deliberately **not** a taxi app: no professional drivers, no dispatch, no fares.

**Stack:** Laravel 13 REST API (PHP 8.4, MySQL) · Expo SDK 54 / React Native / TypeScript mobile app
**Status:** working product in active development (last commit this week)

## What I built
- Phone-number sign-in with one-time codes (no passwords by design), numbers normalised to E.164 so one person
  cannot become four accounts.
- Trip posting and search, seat booking, cancellation, ratings, in-app messaging, driver verification.
- Payments flow and earnings screens, live ride tracking.
- A local-only developer console (SMS outbox, request tester, seed/reset) to speed up development.

## Engineering decisions I'm proud of
- **Seat counts are the one real race.** Two people accepting the last seat at the same moment is handled with a
  row lock in the check-and-decrement, and `seats_available` is an *unsigned* column so the database refuses to go
  negative even if the lock were bypassed. Both layers are tested.
- **Tests run against MySQL, not SQLite**, because the schema depends on strict mode and row locking that SQLite
  does not reproduce.
- **Money is a "contribution", never a fare**, in column names, API fields and UI copy, because Uganda's PSV
  licensing applies to commercial transport. Amounts are whole-shilling integers, so no float rounding.

## Relevance
Trips, status changes, tracking, payments and role-based access: the same building blocks as a fleet or delivery
platform.

<!-- TODO before publishing: add 3-4 screenshots (search, booking, ride tracking), confirm the test count by
running `php artisan test`, and add a "Run it locally" link to the README. -->
