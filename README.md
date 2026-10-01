# Are you found by AI? MCP server

Hosted MCP server for [Are you found by AI?](https://areyoufoundbyai.com), the AI visibility
tool built by Tech Horizon Labs. The product asks AI engines the questions a business's buyers
actually type, records whether the business is named, who is named instead and which sources the
engines read, and re-measures every week. This server gives the business owner's own AI live
access to that measurement mid-conversation.

## Try it now, no account

Add this URL to Claude, Cursor, or any MCP client as a remote server (Streamable HTTP):

```
https://areyoufoundbyai.com/mcp/demo
```

The demo is connected to our own live monitoring of areyoufoundbyai.com, so you are
interrogating real production data. Ask your AI: "how visible is this business to AI, and what
would you fix first?"

## What your AI gets

Nineteen read tools over live measurements, plus one action on paid monitors:

- `get_visibility`: AI Visibility and AI Readiness scores (0 to 100) with trend
- `get_answers`: the answer each engine gave to each tracked buyer question, with the competitors it named and the web searches it ran first
- `get_question_trajectories`: question-by-question history across the engines
- `get_rivals` / `get_share_of_voice`: who AI names instead of you, and how often
- `get_cited_queries`: the questions where a given competitor gets named
- `get_mentions`: new pages on the web that mention the business
- `get_fix_plan`: the prioritised fix plan, in plain language
- `get_citation_sources`: the sources the engines actually cite
- `get_source_profile`: a profile of any cited source, including where a business gets listed on it
- `get_post_brief`: a content-drafting brief built from verified data
- `get_ai_traffic`: AI-referred visitors measured on the business's own site
- `get_agent_view`: what an AI agent's browser actually sees on the site
- `get_crawler_access`: which AI crawlers the site's robots.txt allows or blocks
- `get_schema_evidence`: the structured data in the site's HTML compared with what renders
- `get_regional_visibility`: naming results by area
- `get_benchmark`: the business against its category on our index
- `get_personas`: the buyer personas behind the tracked questions
- `get_context`: the full weekly pack in one call
- `request_rescan`: a capped live re-measure (paid monitors only)

## Customers

Every monitored site gets its own endpoint at `https://areyoufoundbyai.com/mcp/<token>`,
and agency fleets get one connector for the whole network. Setup guide, with a one-click Cursor
link and the Claude Code command: [areyoufoundbyai.com/guides/connect-your-ai](https://areyoufoundbyai.com/guides/connect-your-ai)

The measurement method is open source: [techhorizonlabs/thl-open](https://github.com/techhorizonlabs/thl-open).

## Registry manifest

[`server.json`](./server.json) is the manifest for the official MCP registry.

Tech Horizon Labs, Noosa, Australia. hello@techhorizonlabs.com
