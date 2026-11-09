# rejected

what not to reach for. read this before adding anything that isn't in [the stack](README.md#the-stack). if you add something anyway, say why.

## retired

used before and replaced. existing projects can keep these. new projects shouldn't.

| was | now | why |
| --- | --- | --- |
| clerk | better auth | better auth covers every case, including heavy multi-role apps, without a vendor dashboard |
| radix | base ui | shadcn's default since july 2026, built by the same people |
| lucide | phosphor | weights and fill states let icons match the type |
| framer-motion | motion | same library, new package |
| eslint + prettier | biome | one fast tool |
| prisma + postgres | convex | one backend for data, search, files, jobs, and realtime |
| npm, yarn | pnpm | |
| newsreader | source serif 4 | preferred the reading texture |
| jetbrains mono | commit mono | quieter, and reads less like an editor screenshot |

## never

| what | why |
| --- | --- |
| sentry and other external error services | heavy. write errors to a convex table and show them in an admin tab |
| langfuse and most llm observability tools | bad trace uis. raindrop is the exception worth learning from. store opentraces in convex |
| cloudflare | won't use |
| php | slopware |
| unmaintained packages | slopware, however good they once were |
| raw html where shadcn has a component | inconsistent and inaccessible |
| inline styling everywhere | componentize, and pull values from tokens |
| fake-hacker monospace aesthetics | mono as a costume. it works when the content really is text for machines (pierre) or the product's voice (mintlify); otherwise be technical through clear hierarchy (oxide) |
| stock shadcn gray with no theme | the default theme is a starting point, not a design |
| gradient blobs, glassmorphism for its own sake, emoji in ui | generic ai-template look |
| "agents" without tools | an agent can always call tools and take multiple steps |
| google fonts over the network | self-host with fontsource |
| `pip install` | `uv add` |
