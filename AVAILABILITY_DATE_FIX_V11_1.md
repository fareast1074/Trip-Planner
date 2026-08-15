# Trip Planner V11.1 — Availability Date Fix

Fixed the Create Plan availability flow so a stale “Busy” / “Checking…” state does not remain after dates change.

## Behavior
- Changing Start date automatically re-checks availability.
- Changing End date automatically re-checks availability.
- Changing traveler usernames automatically re-checks availability.
- Manual “Check their availability” still works.
- Older async checks cannot overwrite newer date results.
- Invalid date ranges show an immediate validation message.
