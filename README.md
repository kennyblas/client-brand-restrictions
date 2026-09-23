# Client Brand Restrictions

Small internal site to record which brands a client must **not** be ordered/listed for (e.g. C&D).

- **Database:** Supabase project `Test1` → table `public.client_restrictions`
- **Access:** login required (Supabase Auth email/password). Row Level Security allows only signed-in users.
- **Frontend:** single `index.html` (supabase-js from CDN).

## Use
1. Add team users in Supabase → Authentication → Users → *Add user*.
2. Open the site, sign in.
3. **Order check:** type client (and brand) → red = do not order, green = OK.
4. **Add restriction** when the team posts a new one. "Remove" soft-deletes (sets `active = false`).

## Schema
| column | type |
|---|---|
| client_name | text |
| restricted_brand | text |
| reason | text |
| notes | text |
| reported_by | text |
| active | boolean |
| created_at | timestamptz |
