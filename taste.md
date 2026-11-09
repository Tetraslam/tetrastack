# taste

references for calibration, not templates. don't overindex and don't underindex: work out *why* each one works, then build something that's yours. open the source and look at it (with screenshots if you're an agent) before borrowing from it.

the full collection, with images, lives at [tetraslam.world/taste](https://tetraslam.world/taste) ([markdown](https://tetraslam.world/taste.md)). entries below link to it.

## house style

how this shows up in my own work. taken from parc's tokens:

- **surfaces are steps.** sidebar < background < content < raised, a few percent apart in lightness. warm off-white paper (`#e9e8e3`), never pure white. near-black ink, never pure black.
- **state is an ink overlay at a fixed strength.** hover and press are translucent ink layered over whatever surface they sit on, so they look the same everywhere and nest (a hover on a row, then a stronger one on a control inside it).
- **one hue.** everything is neutral except a single accent (parc's ember, `#d5683f`) that means alive, arriving, or yours. a second hue has to earn its place.
- **named motion.** a standard ease (`cubic-bezier(0.2, 0.8, 0.2, 1)`) plus a morph curve for shape changes. 140 / 220 / 380ms. nothing bounces.
- **text set for reading.** a 62ch measure, a 680px main column, inter for ui, a serif (newsreader) for anything editorial, mono only for code and numbers.
- **lowercase, warm copy.** interfaces talk like a person.

## the bar

three elements from my own work that show how much detail is possible. hold anything new to this standard, then use the details below as a checklist.

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
- a hero sentence that starts in ink and continues in light gray ("wallets. payments. cards..."), with a small grainy gradient tile morphing inline in the text.
- the product screenshot sits in a frame of dithered grain, so it reads as an object, not a pasted image.
- agents get soft gradient swatches as avatars, which gives each identity a color without illustrating anything.
- lots of whitespace, near-black pill buttons, and a single typeface.

### [mintlify agent score](https://www.mintlify.com/score)
- a pixel display font with green as the only accent. mono and pixel type work here because they're the voice of the product (a score for agents), not an excuse to look technical.
- an "agent mode" toggle in the page header, so the page itself practices what it measures.
- live counters, tick-mark rules between sections, a dashed grid frame, and keycap hints (`S` share, `A` agent mode).

### [tnkr](https://www.tnkr.ai/) · [entry](https://tetraslam.world/taste/kh78ry65qecjc209pqps832jks827rty)
- greco-futurism: an ionic pillar, blue sky, an open atmospheric feel. the imagery says trust and foundations.
- a fast, clean screen recording of the real product, preloaded with a rich project.

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

## libraries that are also taste

these are in the stack too. what i notice about them:

- [torph](https://torph.lochie.me/) ([entry](https://tetraslam.world/taste/kh76xybmp495jwd6t69p30rch9842sze)): the right way to morph text in interfaces.
- [paper shaders](https://shaders.paper.design) ([entry](https://tetraslam.world/taste/kh7dsr8pp1tnj1z557fb3t3z3h827nfp)): effects go on top of regions with no foreground text. dither over animation looks incredible.
- [dither plugin](https://dither.floriankiem.com/) ([entry](https://tetraslam.world/taste/kh7ftpadt1jrcw6z4m3q1k5shn827e7b)): mono or color, gradient-like falloff, dither over gifs.
- [dot matrix](https://dotmatrix.zzzzshawn.cloud/) ([entry](https://tetraslam.world/taste/kh7f24n9nf239t9b2cba2hd5c585p39x)): loaders with character.
- [conway](https://rankdim.github.io/conway/) ([entry](https://tetraslam.world/taste/kh78pbrcynwttnd7skvk67qxjh827qtr)): structure, speed, steady novelty, palette.
- [vgpu](https://vgpu.sh/), [streamdown](https://streamdown.ai/), [nuqs](https://nuqs.dev/), [tiptap](https://tiptap.dev/), [cmdk](https://github.com/dip/cmdk), [use-stick-to-bottom](https://github.com/stackblitz-labs/use-stick-to-bottom): small tools that each do one job extremely well.
