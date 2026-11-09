# app

the frame every web project starts in.

### [next](https://nextjs.org) 16
the default for anything with a server, auth, or more than one page.
- **reach for it when**: it's a product, a site with data, or anything deployed to vercel.
- **watch out**: this version is newer than most agents' training data. read `node_modules/next/dist/docs/` before writing code, and keep the agent rules block `next dev` writes into `AGENTS.md`.
- **shipped in**: parc, tetravoice, tetraslamworld, rev-website, tetrachat, softmax

### [vite](https://vite.dev)
the default when it isn't a next app: spas, tools, desktop shells, playgrounds.
- **reach for it when**: no server rendering, no routes worth a framework.
- **shipped in**: tetrapod, paintbrush, omarchy-wrapped

### [pnpm](https://pnpm.io)
the only package manager. pin it with `packageManager` in `package.json`.
- **not this**: npm, yarn.

### [mise](https://mise.jdx.dev)
pins node and other tool versions per project in `mise.toml`.
- **shipped in**: parc

### [tailwind](https://tailwindcss.com) 4 + [tw-animate-css](https://github.com/Wombosvideo/tw-animate-css)
styling. design tokens live in css variables, so components read semantic names instead of raw colors.
- **watch out**: tailwind is the mechanism, not the design. see [taste](../taste.md#house-style) for the token system.
- **shipped in**: everything

### [biome](https://biomejs.dev)
lint and format in one fast tool.
- **reach for it when**: always, for next and vite projects alike.
- **not this**: eslint + prettier.
- **shipped in**: parc, tetraslamworld, softmax, damnbruh-website

### [oxlint](https://oxc.rs)
extra lint pass in vite projects, next to biome.
- **shipped in**: tetrapod, paintbrush, omarchy-wrapped

### [zod](https://zod.dev) 4
schemas at every trust boundary: forms, api routes, agent tool inputs, env.
- **shipped in**: parc, softmax, tetrachat, tetraslamworld

### [nuqs](https://nuqs.dev)
typesafe url search params as state. filters, tabs, open panels, and selected items belong in the url so they survive reloads and can be shared.
- **shipped in**: parc, tetravoice, fashion

### [fontsource](https://fontsource.org)
self-hosted fonts, no google fonts request. four roles, no more. ui and code are fixed defaults; reading and display are favorites that a project's brief may replace:

| role | face | package |
| --- | --- | --- |
| ui | inter | `@fontsource-variable/inter` |
| reading | source serif 4 | `@fontsource-variable/source-serif-4` |
| code, numbers | commit mono | `@fontsource/commit-mono` |
| display | shippori mincho b1, extrabold | `@fontsource/shippori-mincho-b1` |

- **reach for display when**: titles, heroes, empty states, title-card moments. it's the evangelion register (matisse eb's cousin, and it sets japanese too), so use it sparingly and big. never for body or ui.
- **watch out**: shippori's latin and japanese subsets are separate files. load only the subsets the page uses.
- **not this**: newsreader, jetbrains mono (retired). berkeley mono on the web: a separate, pricier license, and it has become the ai-startup signature.
- **shipped in**: parc and tetravoice use the older set (inter, newsreader, jetbrains mono)

### [next-themes](https://github.com/pacocoursey/next-themes)
light/dark switching without a flash. design both themes on purpose, not dark as an inverted afterthought.
- **shipped in**: parc, tetraslamworld, softmax
