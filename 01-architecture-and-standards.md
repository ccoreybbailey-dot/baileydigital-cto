# Architecture & Standards

The default stack and the patterns earned through real builds. New work starts here
instead of re-deciding from scratch. Deviate only with a reason — and log it in
`03-decision-log.md`.

## Default stack

- **Frontend:** React + Tailwind
- **Backend / data / auth:** Supabase (Postgres, auth, edge functions)
- **Hosting:** Vercel
- **AI:** Claude API, called server-side only
- **Email:** Resend
- **PWA by default** for field tools (installs to phone home screen; works where
  signal is bad)

## Patterns settled on

- **Server-side AI only.** Every Claude API call runs through a Supabase edge function
  so the key is never exposed client-side (e.g. `sheet-ai-assist`).
- **Deactivate, never delete.** Rosters and reference data get a deactivated flag, not
  a hard delete — preserves history, avoids orphaned references.
- **Outbox pattern for offline.** Field tools must survive dead signal. Submissions
  queue locally and sync when connectivity returns.
- **Atomic writes via Postgres RPC.** Multi-table writes go through one atomic RPC
  (e.g. `submit_sheet`) so a sheet either fully lands or doesn't — no half-saved state.
- **Auto-save with debounce.** In-progress work persists locally as you type, so a
  crash or force-quit doesn't lose a day's entry.
- **Merge over duplicate.** Prefer one configurable component over near-identical
  copies (e.g. `SheetForm` replaced separate daily/unassigned sheet components).

## Integrations stance

- **CSV export is the 80% solution** for accounting. Ship that before any direct
  integration.
- Among small Quebec trades shops, **Acomba is more common than QuickBooks.** Weigh
  that before building any accounting integration. Build one only if customers ask.

## Field-tool principles

- Built for bad signal, gloved hands, and no patience. Offline resilience and few taps
  beat feature richness.
- **Numbers that matter** (hours, quantities) are always human-confirmed — never
  silently auto-filled by AI.
