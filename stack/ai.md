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

### [streamdown](https://streamdown.ai)
markdown rendering that copes with partial streamed text. add the `@streamdown/code`, `math`, `mermaid`, and `cjk` plugins as needed.
- **shipped in**: parc, tetrachat, tetravoice

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
