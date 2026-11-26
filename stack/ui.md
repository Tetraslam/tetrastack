# ui

components and interaction primitives.

### [ui sdk](https://ui-sdk.dev)
vercel labs' library of headless interaction behaviors (popup, selection, typeahead, roving focus, reorder, resize, viewport, virtualizer, 50+ total) that compose into any component, with first-class WebMCP support so agents can read and drive the page directly. go straight here when building interfaces: working from behaviors instead of pre-baked widgets forces complete control and deliberate interaction design. unstyled, so style with tailwind tokens. `@ui-sdk/react` + `@ui-sdk/core` (react 19+, also works outside react), and it ships a skill: `pnpm dlx skills add vercel-labs/ui --skill ui-sdk`.
- **watch out**: in beta (`0.1.0-beta.*`), so apis may still move.

### [shadcn/ui](https://ui.shadcn.com) on [base ui](https://base-ui.com)
the stock component base when you want a standard finished primitive fast instead of composing from behaviors. `pnpm dlx shadcn init` uses base ui by default. components are installed source, so theme them heavily and break them into small reusable parts instead of styling inline.
- **watch out**: never hand-roll raw html for a dialog, menu, or select — use ui sdk or shadcn.
- **not this**: radix for new projects. existing radix apps (parc, tetravoice) stay as they are. migrate with `pnpm dlx skills add shadcn/ui`, one component at a time.
- **shipped in**: everything

### [phosphor](https://phosphoricons.com)
the icon set. six weights (thin to bold, plus fill and duotone), so icons can match the weight of nearby text, and fill can mark the active state. set `iconLibrary` to `phosphor` in `components.json`, or run `pnpm dlx shadcn migrate icons --from lucide --to phosphor`.
- **reach past it when**: the product needs an icon phosphor doesn't have ("streak", "invoice sent"), or a look of its own. [draw-icons](https://skills.ronykax.com/draw-icons) is a skill that has the agent draw the whole set as plain svgs from a few rules, so corners, stroke and size match, and checks each at the sizes it ships at. `npx skills add ronykax/skills --skill draw-icons`. bookmarked, not yet tried here.
- **not this**: lucide for new projects.
- **shipped in**: fashion, tetrapod

### [cmdk](https://github.com/dip/cmdk)
the command palette. every app with more than a few actions gets ⌘k.
- **shipped in**: parc, tetravoice, tetraslamworld, tetrachat

### [sonner](https://sonner.emilkowal.ski)
toasts.
- **shipped in**: parc, tetravoice, tetraslamworld

### [tiptap](https://tiptap.dev)
rich text editing: composers, posts, notes. pair it with `@tiptap/markdown` so content stays portable.
- **shipped in**: parc, tetraslamworld

### [dnd-kit](https://dndkit.com)
drag-to-reorder for lists, bookmarks, and boards.
- **shipped in**: parc, tetraslamworld

### [use-stick-to-bottom](https://github.com/stackblitz-labs/use-stick-to-bottom)
chat and log views that follow new content without fighting the user's scroll.
- **shipped in**: parc, tetrachat, tetravoice

### [hitbox](https://marcelochaman.com/repository/hitbox)
bigger click and touch targets without moving anything. tailwind utilities that put one `::after` behind a control and stretch it past its edges: `relative hitbox hitbox-2`, per axis (`hitbox-x-2`) or per edge (`hitbox-bottom-2`). css only, 5 kb, no javascript. `pnpm add -D @regular-ppl/hitbox`, then `@import '@regular-ppl/hitbox'` after tailwind.
- **reach for it when**: icon buttons, checkboxes and anything else smaller than a fingertip, and rows whose hover should fill the padding around them. `hover:hitbox:bg-muted` and `focus-visible:hitbox:ring-2` style the stretched surface, so the highlight and the target are the same shape.
- **watch out**: published 2026-11-22 at 0.1.0, so pin it. needs tailwind 4.1 and a positioned control. it takes the control's `::after` and sets `isolation: isolate` on it. neighbors' targets can overlap, so give them separate space, and a parent that clips overflow cuts the target off. disabled controls get no extension.

## comes with shadcn

some shadcn components install these as dependencies. they're fine where a component needs them, but don't choose them on purpose: vaul (drawer), embla (carousel), input-otp, react-day-picker, react-resizable-panels, react-hook-form, date-fns.

## contextual

- [recharts](https://recharts.org): charts, through shadcn's chart component.
- [mapbox-gl](https://docs.mapbox.com/mapbox-gl-js): maps (tetraslamworld travel).
