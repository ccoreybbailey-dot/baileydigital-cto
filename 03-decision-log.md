# Decision Log

Plain-English record of significant calls — what, the options, why. Newest at top, one
entry per real decision. This is what lets an AI reason like a CTO who remembers,
instead of re-opening settled questions.

> Seeded from history as of 2026-06-20. Verify and correct.

### Voice input — scrapped, then re-scoped as voice-to-sheet
First voice-to-text attempt was built and scrapped: poor transcription quality and
awkward UX on job sites. Re-scoped with guardrails rather than abandoned — a guided
question flow, constrained to existing rosters and dropdowns, that pre-fills (never
replaces) and always has a human confirm numbers. **Lesson:** on job sites, constrain
AI input to known options rather than open transcription.

### Offline architecture — outbox + atomic RPC
Field environments have dead signal. Chose an outbox-based submission flow plus an
atomic `submit_sheet` RPC and debounced auto-save, so work is never lost and never
half-saved. Also fixed an auth bug where a token refresh while offline crashed the app.

### Accounting — CSV export over integration
Deferred QuickBooks integration in favor of CSV export as an 80% solution. Acomba is
more common than QuickBooks among small Quebec trades shops, so a specific integration
is a bigger bet than it looks. Revisit only if customers ask.

### Server-side AI via edge function
Moved the description AI-assist to a Supabase edge function (`sheet-ai-assist`) rather
than calling Claude from the client, to keep the API key off the client. Now the
standard for all AI features.

### Component merge — SheetForm
Merged `DailySheet.jsx` and `UnassignedSheet.jsx` into one configurable `SheetForm`.
Less duplication, one place to fix bugs.

### Go-to-market — phased, local-first
Phase 0: capture proof points from the Bessette pilot. Phase 1: single channel —
Facebook in Quebec French + direct English outreach to bilingual landscaping owners
Corey knows. Phase 2: paid acquisition only after there are paying customers.
Explicitly rejected Canada-wide expansion and a time-clock feature — both erode the
local-relationship positioning that is ChantierLog's actual advantage. Five bilingual
companies lined up for staggered 60-day time-boxed pilots, each ending with an
explicit money conversation.

### Standing discipline — validate before building
Corey's default is to build features instead of having the harder customer
conversations. The sequence is: **validate with real users → then build.** A new
feature is not progress if the current one isn't validated.
