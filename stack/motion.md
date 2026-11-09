# motion

animation, shaders, and generative texture. this layer does the most to make something feel alive instead of templated.

### [motion](https://motion.dev)
layout transitions, presence, gestures. load features lazily (`LazyMotion` + `domAnimation`) so the bundle only pays for what's used.
- **not this**: `framer-motion` (the old package name).
- **shipped in**: parc, tetravoice, tetrachat

### [torph](https://torph.lochie.me)
dependency-free text morphing. the right way to animate text that changes in place: labels, counters, status lines.
- **shipped in**: parc, tetravoice, rev-website, fashion

### [paper shaders](https://shaders.paper.design)
shader components for react (`@paper-design/shaders-react`). best on regions with no text over them, and best when they respond to interaction, like the dithering warp in delve-onsite's upload area that changes color and speeds up on hover.
- **shipped in**: tetravoice, tetrachat, re-zero, delve-onsite, rev-website

### [vgpu](https://vgpu.sh)
webgpu surfaces and effects. share one low-power device across the app, import it lazily, and fall back cleanly when there's no webgpu.
- **shipped in**: parc

### [dither-plugin](https://dither.floriankiem.com)
a tailwind plugin for dither effects, in mono or color, over images, gradients, and animations.
- **shipped in**: parc, tetraslamworld

### [dot matrix](https://dotmatrix.zzzzshawn.cloud)
dot-matrix loader animations, compatible with shadcn. use it in place of a stock spinner.

### [conway](https://rankdim.github.io/conway/)
game of life embeds (`@rankdim/conway`). good patterns need structure, a decent speed, steady novelty, and evenly spread clusters. the palette matters as much as the pattern.
- **shipped in**: tetraslamworld

## contextual

- [three](https://threejs.org) + [react-three-fiber](https://r3f.docs.pmnd.rs): real 3d scenes (tetraslamworld's illustrated terrace). reach for paper shaders or vgpu first.
