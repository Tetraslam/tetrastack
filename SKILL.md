---
name: tetrastack
description: tetraslam's curated web stack (libraries, taste references, and rejections). Use when starting, scaffolding, or designing any web app, site, frontend, or full-stack project, when choosing a library or dependency for one, or when the user says to use tetrastack. Also use when the user asks to add, record, retire, or reject a library or reference "in tetrastack".
---

# tetrastack

Two jobs: build with the stack, and record into it.

All paths below are relative to this file. If the skill isn't installed locally, read the same files from `https://raw.githubusercontent.com/tetraslam/tetrastack/main/`.

## Build with it

1. Read `README.md` for the index. Load only the `stack/` layers the project needs. A CLI never needs `stack/motion.md`.
2. Default to the listed picks. Before adding any dependency that isn't listed, check `rejected.md`. If you still add something unlisted, give a one-line reason in your reply.
3. Respect `watch out` notes. They come from real incidents and advisories.
4. For anything visual, read `taste.md`, then write `BRIEF.md` from `brief.md` before any UI code. Pick the direction that suits this product best, from taste.md's list or any style not listed there, then study it from primary sources (real frames, pages, objects; screenshot them) before designing. Never theme from memory. None is the default; the attractors listed in taste.md need an explicit argument. Derive this project's own palette, accent, and identity, and state how it differs from the closest existing project. Decide autonomously: commit the brief and build from it without waiting for approval. Never use another repo's CSS or tokens as a visual starting point (parc, tetravoice, and the rest); link them only for mechanisms. Hold every screen to the constants and the bar: hierarchy first, every state designed, no layout shift, focus and scroll restored. Open the references the brief names (screenshot them with a browser tool if you have one). Borrow the reasoning behind a reference, never its layout or a move marked **signature**.
5. For anything with data or an agent, follow `perf.md`. Optimize what the user feels: prefetch what's one click away, make the first paint the real page, never flash a skeleton, never shift the layout, and make agent work visible while it happens.
6. Check the current docs of each pick before writing code (Context7, or the docs inside `node_modules`). Versions move faster than this file.
7. Before calling the UI done, check the build against `BRIEF.md` point by point and fix any drift.
8. Record the stack you chose in the new project's README or AGENTS.md as a short `stack` section, so later sessions inherit the decisions.

## Record into it

Requests like "add X to tetrastack", "tetrastack reject Y", or "retire Z for W".

1. Find the right file: a `stack/` layer, `taste.md`, `perf.md`, or `rejected.md`. Use the layer's `contextual` section for picks that are only right for some projects.
2. Write the entry in the same shape as its neighbors. For a stack pick:
   ```md
   ### [name](url)
   one line on what it is and why.
   - **reach for it when**: ...
   - **watch out**: ... (optional)
   - **not this**: ... (optional)
   - **shipped in**: ... (optional)
   ```
   Fill `shipped in` by searching `package.json` files under `~/Programming` if that directory exists. Taste entries keep the user's own observations in lowercase, close to their wording, and link the tetraslam.world entry when one exists.
3. Check that the link resolves. Don't invent claims about the library. If the user's reason is thin, ask one question rather than padding it.
4. If a retirement or rejection contradicts an existing entry, update both places.
5. Commit with a short message (e.g. `Add torph to motion`) and push to `main`.
