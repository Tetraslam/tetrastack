# content

rendering code, math, diagrams, and long-form text.

### [@pierre/diffs](https://diffs.com)
diff and code rendering from pierre computer. it's built like devtools should be, and it's very extensible.
- **shipped in**: tetracorp-website

### [@pierre/trees](https://trees.software)
file tree rendering from the same team as diffs. fast and very customizable. pair the two for anything that shows a repo.
- **reach for it when**: file browsers, artifact trees, agent workspaces.
- **watch out**: still in beta (1.0.0-beta.6 as of november 2026).

### [shiki](https://shiki.style)
syntax highlighting. keep highlighter state per code block, keyed, and async.
- **shipped in**: parc

### [katex](https://katex.org)
math rendering.
- **watch out**: parc pins 0.18.2 across every dependency that pulls it in, for GHSA-238p-pmpm-9mq7. load its global styles explicitly.
- **shipped in**: parc, tetraslamworld, tetracorp-website

### [mermaid](https://mermaid.js.org)
diagrams from text. use the elk layout for anything bigger than a few nodes.
- **shipped in**: tetracorp-website

### [unified](https://unifiedjs.com) (remark + rehype)
the markdown pipeline for blogs and docs: gfm, math, sanitize. run rehype-sanitize on anything a user wrote.
- **shipped in**: tetraslamworld, tetracorp-website
