# Changelog — josh-ecu-intake

All notable changes to the customer intake form.

## 2026-07-02

- Audited for the Supabase RLS lockdown (see below). No app changes needed — confirmed this app writes only via the `ecu-intake` n8n webhook and never touches Supabase directly, so it was unaffected by the policy changes.

### Found, not fixed (out of scope)
The `ecu-intake` n8n webhook (`https://n8n.braxtonjeht.com/webhook/ecu-intake`) is currently returning 404 "workflow not registered" — it appears inactive. **Live customers currently cannot submit orders through this form.** This is unrelated to the RLS work and n8n workflows were explicitly out of scope for that change — needs to be reactivated on the n8n VPS.

### Shared backend
The Supabase project this app writes to (`josh-ecu-shop`) had its RLS policies locked down on this date — see [josh-ecu-dashboard/CHANGELOG.md](https://github.com/braxtonjeht-commits/josh-ecu-dashboard/blob/main/CHANGELOG.md) for the full writeup.
