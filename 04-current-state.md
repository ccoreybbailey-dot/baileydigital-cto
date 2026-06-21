# Current State

> Last updated: **2026-06-20** — update this at the end of every work session.

## Now (active)

ChantierLog offline-resilience overhaul just landed: atomic `submit_sheet` RPC,
outbox submission flow, debounced auto-save, and the offline token-refresh crash fix.

## Next (the parked queue)

1. Verify materials-row survival across a force-quit-while-offline.
2. Build the "appliquer à toute l'équipe" crew-hours autofill checkbox.
3. Fix the draft feature's broken save button (the hidden UI).
4. Document the voice-to-sheet feature in a Google Doc (scoped, not built).

## Known bugs — intentionally deferred

- Offline cold-start shows an infinite spinner.
- PWA cache requires a hard-clear after every deploy.

## Go-to-market

- Pitching is blocked until the work week. Five bilingual pilot companies identified
  for staggered outreach.
- Next GTM action: [fill in — e.g. first outreach message to pilot company #1].

## The honest priority check

The biggest risk right now is building instead of validating. The Bessette pilot and
the five-company outreach are the real unlock, not more features. When choosing what
to do next, default to **the conversation over the build.**
