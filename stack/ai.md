# ai

models, agents, and the interfaces around them.

an agent always has tools and can take multiple steps on its own. one-shot prompting with search grounding switched on is not an agent.

### [vercel ai sdk](https://ai-sdk.dev)
the agent loop, tool calling, streaming, structured output, embeddings, transcription, and speech.
- **reach for it when**: any llm call from typescript.
- **shipped in**: parc, tetrachat

### [vercel ai gateway](https://vercel.com/ai-gateway)
one key for every model, with oidc auth on vercel. use a separate project-scoped key for long-running convex actions.
- **not this**: a separate sdk per provider.
- **shipped in**: parc

### [openrouter](https://openrouter.ai)
for models the gateway doesn't serve, including audio. self-hosted servers on modal should accept the same request and response shapes.
- **shipped in**: tetravoice

### [ai elements](https://elements.ai-sdk.dev)
shadcn-style components for chat, tools, reasoning, sources, and prompt input. installed as source you own, so adapt them freely and review your changes when updating from the registry.
- **shipped in**: parc

### [@pierre/words](https://diffs.com/words)
streaming markdown from pierre computer, written in webassembly text. the pick for streamed llm text in new projects. `<Markdown isAnimating>` from `@pierre/words/react` completes unfinished emphasis, code and links while text arrives, and the same core renders html on the server and ansi for a terminal. math is built in (tex to svg, no katex), code highlighting comes from `@pierre/highlights`, and mermaid from [pele](https://pele.run).
- **reach for it when**: chat and agent output, or markdown in a cli. the core has no dependencies and the wasm is 96 kb.
- **watch out**: a week old (0.2.2, november 2026), so pin it and expect the api to move. `renderToHtml()` keeps raw html and `javascript:` links, so sanitize it for anything a user or model wrote; the react component and html sessions drop both (checked). no remark or rehype plugins, and component hooks take and return html strings, not react elements. math is laid out with stix two math metrics, which apple systems ship and others approximate.
- **not this**: streamdown, for new work. pierre claims 20x faster; i measured the core at 331 MiB/s against markdown-it's 5 on a 185 kb document, and haven't benchmarked streamdown myself.

### [streamdown](https://streamdown.ai)
markdown rendering that copes with partial streamed text. add the `@streamdown/code`, `math`, `mermaid`, and `cjk` plugins as needed. what the existing projects run. new ones start on `@pierre/words`, and these move when there's a reason to touch them.
- **shipped in**: parc, tetrachat, tetravoice, kiseki

### [opentraces](https://www.opentraces.ai/schema/latest)
the format for storing agent traces. write the trace from `onStepFinish` so it never slows the response, and store each step as its own convex document.
- **reach for it when**: any agent feature users depend on.
- **shipped in**: parc

### outcomes on traces
label traces from what the user did next, the way [raindrop](https://www.raindrop.ai) does with signals. a click, bookmark, or message counts as a likely success. a rephrase within a minute, or leaving without clicking, counts as a likely failure. the admin view then leads with "searches that failed this week" instead of a wall of traces. shadcn's [trace](https://ui.shadcn.com/docs/components/base/trace) component is a starting point for that view.
- **not this**: langfuse.
- **shipped in**: parc

### [firecrawl](https://firecrawl.dev)
web search, scraping, x/twitter, and linkedin (via the fullenrich provider) as agent tools.
- **shipped in**: parc
