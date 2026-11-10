# effective perf

benchmarks don't matter. what the user feels does: the thing they wanted is already there, nothing moves, and they never see the app waiting. a 40ms query behind a skeleton feels slower than a 400ms one that was fetched before they clicked.

## rules

### be ready before you're asked
- subscribe to everything one click away once the current screen has its data. warm whatever a pointer or focus lands on too.
- arguments must match the destination screen's exactly, because the cache only shares identical queries.
- outside convex: next `<Link>` prefetch, [speculation rules](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API) for multi-page sites, and hover/mousedown prefetch for heavy destinations.

### first paint is the real page
- server-render the shell with its data preloaded ([convex `preloadQuery`](https://docs.convex.dev/client/nextjs/app-router/server-rendering)). the first thing on screen is the actual sidebar and header, not a frame waiting to be filled.
- one authentication per connection. every re-auth makes convex re-run every subscribed query.
- deferred bookkeeping (analytics, visit tracking) waits a few seconds so it doesn't compete with data.

### shape data like screens
- one query per surface, returning what that surface renders. no waterfalls of follow-up fetches. load related data in parallel, keyed so it can start before its parent arrives.
- index every filter you query on. paginate anything that grows.
- organize information so the common path needs the least data. the fastest query is the one the screen doesn't need.

### no skeletons on fast loads
- placeholders stay invisible for their first 200ms, so fast loads never flash one.
- when a placeholder does show, it's built from the real surface's classes (a post placeholder *is* a `.post` with blank lines), so content swaps in without anything moving.
- draw as many placeholders as the screen had last time.
- cached screens just appear. fade content in only if a placeholder was actually visible.

### nothing moves
- reserve space for everything: images with dimensions, columns that render (or render a placeholder) from the start, never a rail that pops in late.
- an expanding element grows itself (min/max height on the morph curve) instead of pushing the page. see the composer in [taste](taste.md#the-bar).

### transitions beat snaps
- an expanding element measures its content first, then animates height and opacity on the named curves. no blank frame, no jump, no double render. record it frame by frame to check.
- instant only when nothing changes shape.

### writes are instant
- [optimistic updates](https://docs.convex.dev/client/react/optimistic-updates) for anything the user makes. what they made appears in place immediately, and the server confirms later.

### ship less up front
- lazy-load heavy editors and renderers, then preload them when the browser is idle. a stub stands in until then.
- load streamdown plugins, katex css, and other secondary assets after the page.
- check the gzipped initial js per route. parc went from ~770KB to ~455KB this way, and profiles from 1.1MB.

### measure what users feel
- record paint marks, layout shifts, placeholder-to-content time, and websocket traffic per page.
- delay socket messages on purpose (by about 3s) to freeze the loading state and inspect it.

## agent interfaces

the same rules apply when the wait can't be removed. make the wait legible, and it stops feeling like waiting.

- **show the work.** stream reasoning, tool calls, and sources as they happen. deepseek r1's visible chain of thought made people patient, even fond of it, because waiting turned into watching something diligent work.
- **progress reads as activity, not a spinner.** label what's happening right now ("reading 3 profiles", "searching github"), morph the label as it changes with torph, and use [shimmer](https://ui.shadcn.com/docs/utils/shimmer) on in-progress text.
- **first token fast.** stream everything. write traces and other bookkeeping after the response (`onStepFinish`), never in the hot path.
- **partial results are results.** show the first hits while the search continues, and let the user act on them.
- **interruptible.** the user can stop, redirect, or take over at any point without losing what's already done.

## references

### parc
the source of most of these rules: warmed subscriptions, ghosts that are invisible for 200ms, a server-rendered shell, and per-page perf scripts. private, but the rules above are its `docs/performance.md`.

### [mcmaster-carr](https://www.mcmaster.com)
a catalog of hundreds of thousands of parts that feels instant. pages are server-rendered and aggressively cached, and destinations are prefetched before you click. it looks like 2004 and outperforms nearly every modern store.

### [nextfaster](https://github.com/ethanniser/NextFaster)
mcmaster's approach rebuilt in next on a million products. partial prerendering serves static page shells from the edge and streams in the dynamic parts, and links prefetch the pages they point to. read the source for the next-specific mechanics.

### [linear's sync engine](https://linear.app/now/scaling-the-linear-sync-engine)
the client holds the data, so every action is local and instant, and sync happens behind it. convex subscriptions give you a lot of this. linear shows how far the idea goes.

### [zero](https://zero.rocicorp.dev)
rocicorp's query-driven sync: queries run against a local cache first and then sync. useful as a mental model for designing convex queries that answer instantly.

### deepseek r1
the reference for agent waiting: visible thinking made a slow model feel endearing instead of slow.
