# ui

components and interaction primitives.

### [shadcn/ui](https://ui.shadcn.com) on [base ui](https://base-ui.com)
the component base. `pnpm dlx shadcn init` uses base ui by default. components are installed source, so theme them heavily and break them into small reusable parts instead of styling inline.
- **watch out**: always use a shadcn component when one exists. never hand-roll raw html for a dialog, menu, or select.
- **not this**: radix for new projects. existing radix apps (parc, tetravoice) stay as they are. migrate with `pnpm dlx skills add shadcn/ui`, one component at a time.
- **shipped in**: everything

### [phosphor](https://phosphoricons.com)
the icon set. six weights (thin to bold, plus fill and duotone), so icons can match the weight of nearby text, and fill can mark the active state. set `iconLibrary` to `phosphor` in `components.json`, or run `pnpm dlx shadcn migrate icons --from lucide --to phosphor`.
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

## comes with shadcn

some shadcn components install these as dependencies. they're fine where a component needs them, but don't choose them on purpose: vaul (drawer), embla (carousel), input-otp, react-day-picker, react-resizable-panels, react-hook-form, date-fns.

## contextual

- [recharts](https://recharts.org): charts, through shadcn's chart component.
- [mapbox-gl](https://docs.mapbox.com/mapbox-gl-js): maps (tetraslamworld travel).
