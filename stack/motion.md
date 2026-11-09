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

## to build

### ink reveal
paint bleeding in to reveal an image or surface, extracted from the [david whyte experience](https://davidwhyte.com/experience/) so it works anywhere.
- **mechanism**: a mask that thresholds noise against progress (`smoothstep(p - edge, p, fbm(uv * scale) + bias(uv))`). darken the pigment along the edge band the way watercolor dries, and multiply in paper grain.
- **progress sources**: time (on mount or when it enters the viewport), scroll position, pointer (local progress that falls off with distance from the cursor), or a value you control.
- **knobs**: duration and easing, noise scale and octaves, edge width and darkness, origin and direction (`bias`), grain amount, reveal or conceal.
- **runtime**: a small fragment shader on vgpu with a webgl2 fallback, like parc's field. a css `mask-image` with svg `feTurbulence` could serve as a no-gpu fallback.
- **reduced motion**: show the final state.

## contextual

- kuwahara pass ([painterly shaders](https://blog.maximeheckel.com/posts/on-crafting-painterly-shaders/)): post-processing that turns any rendered scene or image painterly. r3f-friendly.
- [three](https://threejs.org) + [react-three-fiber](https://r3f.docs.pmnd.rs): real 3d scenes (tetraslamworld's illustrated terrace). reach for paper shaders or vgpu first.
