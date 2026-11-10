---
direction: live dither
status: draft
---

# live dither

dark, grainy, with a shader that breathes on the one surface that matters. fits single-purpose tools with one hero interaction.

## sources
- [delve-onsite](https://delve-onsite.vercel.app): the upload field, a live dithering warp that shifts color and speeds up on hover and drag. take: the shader lives on one surface, and every state has its own motion.
- [its source](https://github.com/tetraslam/delve-onsite/blob/master/frontend/src/components/file-upload.tsx): the exact state choreography (color, speed, scale, timings).
- [paper shaders](https://shaders.paper.design): the Dithering component and its parameters.

## avoid
dither as a full-page background behind text, or a static dithered image. the dither reacts, and it lives on the surface that takes input.
