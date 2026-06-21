# BaileyDigital CTO

This is the working memory and standards layer for BaileyDigital — the context an
AI (or future-you) needs to make good technology and product decisions without
re-explaining everything from scratch in every chat.

**The problem it solves:** work spread across dozens of separate chats gets messy.
Decisions get forgotten, standards drift, and you burn limited evening/weekend hours
just rebuilding context. This repo is the single source of truth that fixes that.

---

## How to use it

**Start of a work session** — point Claude at this folder and have it read these
files before doing anything. In Claude Code, a `CLAUDE.md` in your working folder is
read automatically, so the fastest setup is to keep this repo open or reference it
from each project's own `CLAUDE.md`. (Confirm current auto-load behavior in the
Claude Code docs.)

**During the session** — the AI now knows the thesis, the stack, the rules, the
history, and what's in flight. It can act like a CTO with memory instead of a
stranger you have to brief every time.

**End of a work session** (two minutes — this is the habit that makes the whole thing
work):

- Update `04-current-state.md` — what changed, what's next.
- If you made a real decision, add one entry to `03-decision-log.md`.

That's the entire discipline. Two minutes at the end keeps the next chat — and the
next subagent, once you build Layer 2 — instantly oriented.

---

## The files

- `00-thesis-and-portfolio.md` — what BaileyDigital is and what you're building.
- `01-architecture-and-standards.md` — your default stack and settled patterns.
- `02-security-rules.md` — hard rules. Never violate.
- `03-decision-log.md` — why you made the calls you made.
- `04-current-state.md` — what's live, in flight, parked, and next. The living doc.

---

Seeded from history as of **2026-06-20**. Read them, correct anything wrong, fill the
`[bracketed gaps]`. They're yours — own them.
