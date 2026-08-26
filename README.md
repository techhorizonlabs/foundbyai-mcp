# Are you found by AI? — MCP server

Hosted MCP server for [Are you found by AI?](https://areyoufoundbyai.com), the AI-visibility
scanner built by Tech Horizon Labs. The product asks all seven answer engines (ChatGPT, Claude,
Gemini, Perplexity, Grok, DeepSeek, Google AI Overviews) the questions a business's buyers
actually type, keeps every answer verbatim, and re-measures weekly. This server gives the
business owner's own AI live access to that measurement mid-conversation.

## Try it now, no account

Add this URL to Claude, Cursor, or any MCP client as a remote server (Streamable HTTP):

```
https://areyoufoundbyai.com/mcp/demo
```

The demo is connected to our own live monitoring of areyoufoundbyai.com, so you are
interrogating real production data. Ask your AI: "how visible is this business to AI, and what
would you fix first?"

## What your AI gets

Thirteen read tools over live measurements, plus one action on paid monitors:

- `get_visibility` — AI Visibility and AI Readiness scores (0–100) with trend
- `get_question_trajectories` — question-by-question history across the engines
- `get_rivals` / `get_share_of_voice` — who AI names instead of you, and how often
- `get_mentions` — new pages on the web that mention the business
- `get_fix_plan` — the prioritised fix plan, in plain language
- `get_citation_sources` — the sources the engines actually cite
- `get_post_brief` — a content-drafting brief built from verified data
- `get_ai_traffic` — AI-referred visitors measured on the business's own site
- `get_agent_view` — what an AI agent's browser actually sees on the site
- `get_benchmark` — the business against its category on our index
- `get_personas` — the buyer personas behind the tracked questions
- `get_context` — the full weekly pack in one call
- `request_rescan` — a capped live re-measure (paid monitors only; hidden on the demo)

## Customers

Every Stay Found monitor gets its own endpoint at `https://areyoufoundbyai.com/mcp/<token>`,
and agency fleets get one connector for the whole network. Setup guide, including Claude and
Cursor one-click paths: [areyoufoundbyai.com/guides/connect-your-ai](https://areyoufoundbyai.com/guides/connect-your-ai)

The measurement method is open source: [techhorizonlabs/thl-open](https://github.com/techhorizonlabs/thl-open).

## Registry manifest

[`server.json`](./server.json) is the manifest for the official MCP registry.

Tech Horizon Labs · Noosa, Australia · hello@techhorizonlabs.com
