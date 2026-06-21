# Security Rules — Non-Negotiable

These exist because a service role key was once exposed in a chat. That's been
remediated (legacy keys disabled, migrated to the Secret API Keys system). These rules
keep it from happening again.

1. **Never expose secret or service keys.** No API keys, service role keys, or tokens
   in client-side code, in chats, in commits, or in screenshots. AI calls go through
   server-side edge functions, always.
2. **Secrets live in environment variables / Supabase secrets.** Never hard-coded.
3. **If a key is ever exposed, rotate it immediately** — disable the old one, issue a
   new one. Don't wait, don't hope.
4. **Before pasting code or logs into any chat, scan for secrets first.**
5. **Least privilege.** Use the most restricted key that does the job; never the
   service role key client-side.

When in doubt, treat it as exposed and rotate.
