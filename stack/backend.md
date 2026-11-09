# backend

data, auth, email, and the patterns that sit on them.

### [convex](https://convex.dev)
the default database and backend for any new project. it's also the storage, full-text search, vector search, scheduled jobs, and realtime layer, so most "add a service" moments are already handled.
- **reach for it when**: always, unless the project already uses something else.
- **watch out**: documents max out at 1 MiB. split anything that grows without bound (agent trace steps, chat messages) into its own documents.
- **not this**: prisma + postgres, supabase, firebase.
- **shipped in**: parc, tetravoice, tetraslamworld, re-zero, fashion

### [convex-helpers](https://github.com/get-convex/convex-helpers)
`customQuery` / `customMutation` with row-level security. all visibility rules live in one wrapper, and agent tools call the same functions as the ui, as the viewer in question.
- **reach for it when**: there's more than one role, or an agent reads user data.
- **shipped in**: parc

### [convex components](https://www.convex.dev/components)
durable building blocks. [workflow](https://www.convex.dev/components/workflow) for long multi-step jobs like enrichment agents.
- **shipped in**: parc

### [better auth](https://better-auth.com) + [@convex-dev/better-auth](https://github.com/get-convex/better-auth)
auth, roles, magic links, oauth. handles everything from a solo tool to multi-role invite-only platforms.
- **watch out**: stay on 1.6.22 or later (GHSA-qq9h-g4jm-xgf3, magic-link takeover).
- **not this**: clerk.
- **shipped in**: parc, tetravoice, fashion

### [resend](https://resend.com) + [react email](https://react.email)
transactional email written as components. scope sending keys to a subdomain.
- **shipped in**: parc

### errors table, no sentry
catch errors at every boundary you can (react error boundaries, mutation wrappers, route handlers) and write them to a convex `errors` table through one function. show them in an admin tab.
- **reach for it when**: any app with users.
- **not this**: sentry or another external error service.
- **shipped in**: parc

## contextual

reach for these only when the project calls for them.

- [idb-keyval](https://github.com/jakearchibald/idb-keyval): browser-only storage when data should never touch a server (tetravoice keeps reference voices this way).
- [uv](https://docs.astral.sh/uv) + [modal](https://modal.com): the python side, for self-hosted models and gpu jobs. add deps with `uv add`, never by editing `pyproject.toml`.
