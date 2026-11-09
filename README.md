<div align="center">

# tetrastack

**the libraries, references, and rejections behind everything i build for the web**

[stack](#the-stack) · [taste](taste.md) · [perf](perf.md) · [rejected](rejected.md) · [skill](SKILL.md)

</div>

every entry here has shipped in a real project ([parc](https://parc.rev.school), [tetraslam.world](https://tetraslam.world), tetravoice, and others) or earned its place in my [taste collection](https://tetraslam.world/taste). it's written for agents first: point one at this repo and it builds the way i would.

## use it

ask your agent:

> build me a ____. use github.com/tetraslam/tetrastack for the stack and taste.

to make it permanent, install it as a skill. it then loads on its own whenever a web project starts:

```sh
git clone https://github.com/tetraslam/tetrastack ~/Programming/tetrastack
ln -s ~/Programming/tetrastack ~/.agents/skills/tetrastack
```

the skill also handles the other direction. "add torph to tetrastack, it's the right way to morph text" files the entry in the right place, then commits and pushes it.

## the stack

| layer | default picks |
| --- | --- |
| [app](stack/app.md) | next 16 · vite outside next · pnpm · tailwind 4 · biome · zod · nuqs |
| [backend](stack/backend.md) | convex · convex-helpers rls · better auth · resend + react email · an errors table instead of sentry |
| [ai](stack/ai.md) | ai sdk + gateway · ai elements · streamdown · opentraces with outcomes · firecrawl |
| [ui](stack/ui.md) | shadcn on base ui · phosphor · cmdk · sonner · tiptap · dnd-kit · use-stick-to-bottom |
| [motion](stack/motion.md) | motion · torph · paper shaders · vgpu · dither · dot matrix · conway |
| [content](stack/content.md) | @pierre/diffs · @pierre/trees · shiki · katex · mermaid · unified |
| [ship](stack/ship.md) | vitest · convex-test · react doctor · vercel + analytics |

each entry says what it is, when to reach for it, what to watch out for, and where it shipped.

## taste

[taste.md](taste.md) holds the house style (stepped surfaces, ink-overlay states, one hue, named motion curves), the bar (three elements from my own work, described down to the edge cases), and the references that calibrate it: pierre, gwern, nous, prime intellect, palladium, oxide, natural, osmosis, mintlify, tnkr, diffs, pi, and more. each one comes with notes on what to look at.

## effective perf

[perf.md](perf.md): perf is what the user feels. prefetch everything one click away, server-render the real first paint, no skeletons on fast loads, nothing moves, writes are optimistic. agent interfaces make the wait legible instead. references: mcmaster-carr, nextfaster, linear's sync engine, deepseek r1.

## rejected

[rejected.md](rejected.md) lists tools i've retired (clerk, radix, lucide, prisma) and things i won't use (sentry, langfuse, fake-hacker monospace). an agent learns as much from these as from the picks.

## license

[mit](LICENSE)
