# taste

references for calibration, not templates. don't overindex and don't underindex: work out *why* each one works, then build something that's yours. never lift a reference's signature move (marked **signature** below where it's tempting). take the principle behind it and find this product's own version. open the source and look at it (with screenshots if you're an agent) before borrowing from it.

the full collection, with images, lives at [tetraslam.world/taste](https://tetraslam.world/taste) ([markdown](https://tetraslam.world/taste.md)). entries below link to it.

## constants

these hold in every project, whatever it looks like.

- **hierarchy before decoration.** on every screen and every row, decide what the reader needs first. give that the weight and let metadata recede (smaller, quieter, or on demand). no row repeats a label the layout already implies.
- **the main artifact leads.** whatever people came to read or use (a trace, a document, a conversation) is the hero, in its natural order. don't hoist summaries, final answers, or overviews above it, and don't dim the parts that carry meaning by default.
- **severity is honest.** loudness matches what actually needs the reader. an alarm fires only when they must act; noise, stale notes, and recovered errors stay quiet. a ui that cries wolf has failed.
- **show the present.** anything that monitors something live says what time it is, whether the thing is alive, and when it next acts. data is live or labeled with its age; never show a stale number as if it were current.
- **every state is designed.** rest, hover, focus, active, loading, empty, error, and success.
- **nothing shifts, nothing is lost.** no layout shift, and focus and scroll return to where they were. see [perf](perf.md).
- **transitions, not snaps.** anything that opens, closes, grows, or swaps transitions from its measured size on the project's curves. instant beats animated only when there's nothing to transition. a flicker or snap costs more perceived speed than a 200ms transition.
- **say less.** no subtitle under every item, no status pills that don't change a decision, no metadata the reader didn't come for. extra info goes on hover or on demand.
- **motion has a purpose.** each project names its own curves and durations and uses them consistently, and reduced motion is respected.
- **identity fits the product.** a social app, a devtool, and a reading site should not share a look. devtools are dense, calm, and legible.
- **copy talks like a person.** lowercase and warm, unless the direction calls for another voice.
- **type**: inter for ui and commit mono for code and numbers by default. the reading and display faces are chosen in the brief. source serif 4 and shippori mincho b1 are favorites, not obligations.

## directions

the look is chosen per project, in a [brief](brief.md) written before any ui code. a direction is studied, not themed: before using one, collect primary sources (real frames, real pages, real objects, not what the style looks like in general), note what makes each work, and build from those. naming a style and then drawing on the average of the internet produces generic slop: chamfered cards, tracked uppercase micro-labels, and a hex wallpaper are not evangelion. the agent picks whatever suits the product best: a direction from this list, a style that isn't listed, or a deliberate blend. the list is a starting range, not a menu. the order here means nothing, and none of them is the default. never start from another project's css or tokens, including parc's.

- **warm paper** (parc): warm off-white surfaces stepped a few percent apart, hover as ink overlays, one accent (ember) that means alive or yours, and a dither field on surfaces that take input. fits places people live in daily: social, messaging, notes.
- **live dither** (delve-onsite): dark, grainy, with a shader that breathes on the one surface that matters and reacts to every state. fits single-purpose tools with one hero interaction.
- **illustrated serif** (tetraslam.world): serif typography, an illustration with a sense of place, considered light and dark. fits personal and editorial sites.
- **title card** (evangelion): black and white, a heavy mincho set huge, stretched or squeezed, in broken stacked layouts, cut in hard. fits launches, story-driven pages, and moments that should feel like an event.
- **kinetic menu** (persona 5): a palette of two or three colors at full contrast, angled shapes, cut-out lettering, and a transition with personality on every action, while staying readable. fits games, playful consumer apps, anything where navigating is the experience.
- **lens** (kyoto animation): soft light, bloom, depth of field, focus pulls as transitions, pastel color, attention to tiny states. fits reflective, personal, and media products.
- **painterly** (kuwahara, oil, ink reveal): paint and watercolor surfaces, often as an atmospheric backdrop behind a precise technical artifact, as on prime intellect's inference page. fits research, creative tools, and anything that should feel made by hand.
- **hardware specimen** (oxide): the look of physical machines, with textured controls, cell grids, and technical clarity without hacker costume. fits infrastructure and serious devtools.
- **raw text** (pierre): the content is the design. markdown, mono, a cursor. fits products for machines and agents.
- **greco-futurism** (tnkr): sky, stone, open space, foundations. fits products that must earn trust.
- **editorial grandeur** (palladium): seriousness, restraint, hope. fits long-form and ideas.
- **native material** (ghostty): the product renders its own pitch in its own medium (ascii in a terminal, a live trace in a trace viewer). fits any product with a strong medium.
- **neobrutalism** ([neobrutalism.dev](https://neobrutalism.dev)): flat saturated color, thick black borders, hard offset shadows, unapologetic type. fits playful tools and anything that should feel direct.
- **skeuomorphism**: real materials and objects (leather, paper, knobs, glass) rendered so controls look like what they do. fits instruments, creative tools, anything tactile.
- **bento grid**: content in tidy tiles of different sizes, each one a self-contained idea. fits overviews, dashboards, product pages with many facets.
- **editorial / magazine**: a strong grid, big headlines, pull quotes, columns, image and type in conversation. fits writing, publications, long reads.
- **scrapbook**: collage, tape, torn paper, handwriting, stickers, things pinned at angles. fits personal, social, memory and collection apps.
- **acid graphics**: chrome, warped type, rave-flyer energy, neon on black, liquid 3d forms. fits music, events, culture, and launches that should feel loud.
- **evangelion / nerv**: emergency orange and red on black, hexagonal panels, condensed warning type, a heavy mincho for titles, system readouts. fits monitoring, ops, anything with alarms. see also title card.
- **art deco**: geometric ornament, gold on deep color, symmetric fans and stepped forms, elegant display type. fits luxury, hospitality, finance with glamour.
- **game boy / 8-bit**: a four-shade palette, a pixel grid, bitmap fonts, chunky sprites. fits games, toys, nostalgic or very constrained interfaces.
- **swiss / international typographic**: a rigorous grid, sans-serif type, asymmetric layout, flat color, lots of white space. fits information-heavy products that need clarity.
- **bauhaus**: primary colors, circles, squares, and triangles, type as construction. fits education, tools, anything about form and function.
- **constructivism**: diagonals, red and black, photomontage, bold sans type as propaganda. fits announcements, movements, activist or community products.
- **memphis**: squiggles, terrazzo, clashing pastels and primaries, playful geometry. fits consumer fun, kids, creative play.
- **risograph / zine**: two or three spot inks, misregistration, grain, photocopied texture, hand-made layouts. fits indie publishing, communities, small-batch creative work.
- **blueprint / technical drawing**: white line on blue, dimension lines, callouts, orthographic views. fits engineering, hardware, robotics, anything that explains how it's built.
- **braun functionalism** (dieter rams): calm off-white and gray, one signal color, precise controls, nothing extra. fits utilities and devices.
- **fui** (film hud): thin lines, scanning grids, telemetry, targeting overlays, sci-fi readouts. fits monitoring, robotics, real-time data.
- **retro os** (classic mac, windows 95): windows, bevels, pixel icons, a menu bar. fits playful tools, personal sites, nostalgia.
- **frutiger aero / y2k**: glossy bubbles, sky and water, aqua glass, optimistic tech. fits consumer apps that should feel bright and hopeful.
- **tufte data-ink**: maximum data, minimum chrome, small multiples, sparklines, labels instead of legends. fits analytics, research, anything numbers-first.
- **transit signage** (vignelli, wayfinding): strict color coding, bold sans labels, lines and stops, arrows. fits navigation, systems maps, routing and status.
- **ukiyo-e / woodblock**: flat color planes, bold outlines, patterned water and sky, a carved line. fits storytelling, culture, and slow, beautiful products.
- **museum archive**: specimen labels, catalog numbers, plates, captions, archival paper. fits collections, research, libraries, taste pages.
- **receipt / thermal print**: narrow mono columns, dotted rules, timestamps, totals. fits logs, transactions, small utilities with personality.
- **solarpunk**: lush green, warm sun, art nouveau curves, optimistic ecology. fits climate, community, and hopeful futures.
- **illuminated manuscript**: drop caps, marginalia, ornament, gold leaf, rubrication. fits reading, scholarship, anything meant to feel precious.
- **hand-drawn sketch** (rough.js): wobbly lines, marker fills, whiteboard energy. fits brainstorming, early-stage tools, explanations.

### attractors

agents fall into these looks without deciding to. choosing one requires an explicit argument in the brief.

- **warm paper**: parc's look, because parc is the best example on disk.
- **generic dark devtool**: graphite surfaces with an indigo, violet, or blue accent, hairlines, and inter.
- **stock shadcn**: neutral gray, default radius, default everything.
- **ai-startup landing**: black, a gradient glow behind the hero, a mono eyebrow line, a logo wall.

## the bar

three elements from my own work that show how much detail is possible. hold anything new to this standard, then use the details below as a checklist. the bar is the level of care, not the look: don't copy these elements' colors or shapes into other products. link to them for mechanisms (state machines, focus restore, render-on-change), not for style.

### the upload field · delve-onsite
the drop zone is a live paper-shaders `Dithering` warp, not a static gradient. on hover or drag it brightens from dormant deep blue (`#0f1a24`) to forest green (`#1a4a3a`), speeds up from 0.2 to 0.6, and the shader layer scales to 1.05 over 700ms while the icon ring scales and tints over 500ms. the submit button fills with a wash from left to right on hover. every state of the surface has its own motion, and they all share one ease-out. [source](https://github.com/tetraslam/delve-onsite/blob/master/frontend/src/components/file-upload.tsx)

### the field · parc
the same idea grown into a material: an ordered-dither (8×8 bayer) fbm shader that appears only on surfaces that take something from you. it has five states (rest, compose, intent, receive, work), each with an energy level from 0 to 1. energy eases toward the current state's level with a 0.22s time constant, the color shifts from cold to warm with it, and a glow follows the cursor.
- it runs on webgpu through vgpu, falls back to webgl2, and caps the pixel ratio at 2.
- it renders only while energy is changing or the texture is moving, and pauses offscreen.
- under reduced motion it snaps to the target and holds still.
- dropping files anywhere on the page puts every receiving field into `receive`.

### the composer · parc
press `n` anywhere:
- if the composer is on screen, it opens in place. if not, it remembers your scroll position and focused element, scrolls the composer to just under the top bar, and opens once scrolling ends (with a 700ms fallback). its field shows `intent` on the way there.
- opening morphs the editor's min/max height on the morph curve (32px to 84px, capped at 45vh). nothing else on the page jumps.
- `escape` closes it and takes you back where you were, focus included. clicking away closes it without scrolling. `⌘enter` posts, the composer closes, and the new post appears in place.
- the edge cases are handled: reduced motion jumps instead of scrolling, a window blur (file chooser, other app) doesn't count as leaving, iOS safari's late blur on tapping "post" doesn't collapse the button before the click lands, and an open mention menu or gif picker gets escape and enter first.

## sites

### [palladium magazine](https://www.palladiummag.com/) · [entry](https://tetraslam.world/taste/kh784zm4w1r5m0914yn6h29839843ktv)
- hope, grandeur, and restraint all at once.
- the design treats the content as something serious.

### [stripe press](https://press.stripe.com)
- books treated as objects worth revering, with the same mix of grandeur and restraint as palladium.
- take that reverence and leave the density. too much is going on at once.

### [oxide computer company](https://oxide.computer/) · [entry](https://tetraslam.world/taste/kh7a3qej7xann5rmbkfv4wwd918436cx)
- the look of physical servers: textured buttons, green cell grids.
- technical and clear without sliding into fake-hacker monospace.
- clear information hierarchy, readable text and graphics.

### [osmosis](https://osmosis.ai/) · [entry](https://tetraslam.world/taste/kh74rntzcgaad0aqnrhy0rsbk5842jtw)
- atmosphere that fits the product (rl hill-climbing): grain and paper texture over graphics, softly animated fog.
- smooth abstract graphics that animate on scroll: manifolds, highlights that morph across text.

### [natural](https://www.natural.com/)
- **signature**: a hero sentence that starts in ink and continues in light gray ("wallets. payments. cards..."), with a small grainy gradient tile morphing inline in the text. the principle is progressive emphasis; don't reuse the fade.
- the product screenshot sits in a frame of dithered grain, so it reads as an object, not a pasted image.
- agents get soft gradient swatches as avatars, which gives each identity a color without illustrating anything.
- lots of whitespace, near-black pill buttons, and a single typeface.

### [mintlify agent score](https://www.mintlify.com/score)
- a pixel display font with green as the only accent. mono and pixel type work here because they're the voice of the product (a score for agents), not an excuse to look technical.
- an "agent mode" toggle in the page header, so the page itself practices what it measures.
- live counters, tick-mark rules between sections, a dashed grid frame, and keycap hints (`S` share, `A` agent mode).

### [nous research](https://nousresearch.com)
a little overbearing taken whole, but a great reference.
- condensed display type filling the full width, a hand-drawn anime mascot as the logo, and an electric-blue frame around the whole viewport.
- the navigation is an agent: a ⌘k bar ("hermes: about nous") sits right under the logo.
- a culture with merch people actually wear. the brand extends past the screen.

### [prime intellect](https://www.primeintellect.ai/model-factory#hosted-training) · [inference](https://www.primeintellect.ai/inference#dedicated)
the product pages, not the homepage.
- product features are explained by small live diagrams of the real thing: a reward curve drawing itself next to its hyperparameters (`max_steps`, `batch_size`, `learning_rate`), an eval list, an observability crosshair labeled logs / traces / metrics / alerts.
- **signature**: diagrams sit inside frames with corner tick marks, like crop marks on a print. the principle is framing artifacts as specimens; don't reuse the ticks.
- a sticky section index on the left with an active bar, and numbered points (1.1, 1.2, ... 1.6) that keep counting across sections.
- the inference page puts a full dashboard (endpoint status, a capacity bar, live-looking charts) on top of a blurred, grainy orange backdrop that looks like paint. a technical artifact on an atmospheric surface.
- headlines that start bright and fade to gray mid-sentence (natural's signature, see above).

### [tnkr](https://www.tnkr.ai/) · [entry](https://tetraslam.world/taste/kh78ry65qecjc209pqps832jks827rty)
- greco-futurism: an ionic pillar, blue sky, an open atmospheric feel. the imagery says trust and foundations.
- a fast, clean screen recording of the real product, preloaded with a rich project.

### [gwern.net](https://gwern.net) · [design notes](https://gwern.net/design)
take the parts that serve "semantic zoom", gwern's term for reading at whatever depth you want without leaving the page:
- recursive popups: hover a link to get an annotation, hover a link inside that, and so on. references open in place instead of sending you away.
- epistemic metadata on every page (status, certainty, importance), so readers know how much weight to give it.
- sidenotes instead of footnotes, collapsible sections, backlinks, and link icons that show where a link goes before you click.
- a markdown version of every page, the same idea as tetraslam.world's `.md` routes.
- leave the boxed nav and the density of controls.

### [camelot.wiki](https://camelot.wiki/citadel/camelot.wiki/about/something+about+the+stars) · [entry](https://tetraslam.world/taste/kh774ckyvjhydb0pv71j9nk5tn84352z)
- dense, high-entropy content with mystique. read the subpages, not just the front page.

### [delve-onsite](https://delve-onsite.vercel.app) · [entry](https://tetraslam.world/taste/kh75zr3ydkchmkzg4dv30y5akd83am3y)
- mine. background grain, the typography, and a live paper-shaders dithering warp on the upload area that shifts from deep blue to forest green and speeds up on hover. the shader breathes. [source](https://github.com/tetraslam/delve-onsite).

## software

### [the pierre computer company](https://pierre.computer)
i love everything they make.
- the corporate site is a page of raw markdown in mono with a blinking cursor: brackets, `#` headings and all. the content is the design, and it fits a company that makes infrastructure for machines.
- every open-source library gets its own focused site, where the hero is the real component running ([trees](https://trees.software) opens on a working file tree beside highlighted code).
- a "for agents" button next to install and docs.
- they write about the craft itself ([on highlighting code](https://pierre.computer/writing/on-highlighting-code), [on rendering diffs](https://pierre.computer/writing/on-rendering-diffs)).

### [diffs](https://diffs.com/) · [entry](https://tetraslam.world/taste/kh752gdpd0j48p75ztnvz9tf8n842wx0)
- extensibility and taste in how the structure is designed.
- devtools should be designed like devtools, and products like products. sometimes it needs to be both.

### [ghostty](https://ghostty.org)
- the hero is an animated ascii ghost running inside a real terminal window, above one sentence and two buttons.
- the product renders its own pitch. the animation is made of the same material as the product (characters in a terminal), so it can't look like generic marketing.

### [pi](https://pi.dev/) · [entry](https://tetraslam.world/taste/kh7ez3wvm2rzd3439b41z9vbv583bypk)
- a great coding agent tui: sane defaults, with extensions that hot-reload so it can improve itself.
- chats as a tree, which fits subtasks and subagents far better than a linear history.

## art direction references

the sources behind several directions. painting styles carried onto the screen. study the technique, then use it as one element on a surface, not as the whole site.

### [on crafting painterly shaders](https://blog.maximeheckel.com/posts/on-crafting-painterly-shaders/) · [entry](https://tetraslam.world/taste/on-crafting-painterly-shaders)
- maxime heckel builds paint, watercolor, and aquarelle looks in webgl from first principles, with a runnable sandbox at every step.
- the kuwahara filter (and its anisotropic version) does most of the work: an edge-preserving blur that turns detail into brushy patches of color.
- what makes it read as paint: no fine texture or normal detail, preserved edges, quantized color.

### [oil paint brush](https://www.shadertoy.com/view/MtKcDG) · [entry](https://tetraslam.world/taste/oil-paint-brush)
- flockaroo's shader repaints live video as oil, stroke by stroke. the strokes follow the image's structure instead of blurring it.
- see also his notebook drawings and ballpoint sketch shaders.

### ink reveal · [david whyte experience](https://davidwhyte.com/experience/)
paint bleeding in to reveal an image. the effect is worth extracting from the site into a standalone, configurable component (see [motion](stack/motion.md#to-build)).

### persona 5 (game ui)
- red, black, and white only. lettering cut out like a ransom note, menus set at angles, jagged shapes, and a transition with personality on every action.
- for all that chaos, text stays high-contrast and the current choice is always obvious. the bar for "stylish but readable".
- the ui is the identity: menus, calling cards, and splash screens all speak the same language as the story.
- [game ui database](https://www.gameuidatabase.com) for more.

### evangelion title cards
- matisse eb, an ultra-bold mincho serif, in white on black: set huge, stretched or squeezed to fill the frame, stacked in l-shaped and broken layouts, and cut in hard on the beat.
- typography with timing. it's hideaki anno's signature and carries into his later work (shin godzilla, shin ultraman).

### kyoto animation (violet evergarden, hyouka, sound! euphonium)
- they animate as if through a real camera lens: bokeh, rack focus, light leaks, a little chromatic aberration, and soft pastel light.
- small physical details carry the emotion: hands, feet, a sleeve, a glance.
- on the web: depth of field and focus pulls as transitions (blur what's no longer in focus instead of fading it), soft light and bloom instead of drop shadows, and attention to tiny states.

## libraries that are also taste

these are in the stack too. what i notice about them:

- [torph](https://torph.lochie.me/) ([entry](https://tetraslam.world/taste/kh76xybmp495jwd6t69p30rch9842sze)): the right way to morph text in interfaces.
- [paper shaders](https://shaders.paper.design) ([entry](https://tetraslam.world/taste/kh7dsr8pp1tnj1z557fb3t3z3h827nfp)): effects go on top of regions with no foreground text. dither over animation looks incredible.
- [dither plugin](https://dither.floriankiem.com/) ([entry](https://tetraslam.world/taste/kh7ftpadt1jrcw6z4m3q1k5shn827e7b)): mono or color, gradient-like falloff, dither over gifs.
- [dot matrix](https://dotmatrix.zzzzshawn.cloud/) ([entry](https://tetraslam.world/taste/kh7f24n9nf239t9b2cba2hd5c585p39x)): loaders with character.
- [conway](https://rankdim.github.io/conway/) ([entry](https://tetraslam.world/taste/kh78pbrcynwttnd7skvk67qxjh827qtr)): structure, speed, steady novelty, palette.
- [vgpu](https://vgpu.sh/), [streamdown](https://streamdown.ai/), [nuqs](https://nuqs.dev/), [tiptap](https://tiptap.dev/), [cmdk](https://github.com/dip/cmdk), [use-stick-to-bottom](https://github.com/stackblitz-labs/use-stick-to-bottom): small tools that each do one job extremely well.
