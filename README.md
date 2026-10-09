# Are you found by AI? MCP server

Hosted MCP server for [Are you found by AI?](https://areyoufoundbyai.com), the AI visibility
tool built by Tech Horizon Labs. The product asks AI engines the questions a business's buyers
actually type, records whether the business is named, who is named instead and which sources the
engines read, and re-measures on a schedule (weekly on Pro, monthly on the free plan). This server gives the business owner's own AI live
access to that measurement mid-conversation.

## Try it now, no account

In Claude Code, one line:

```bash
claude mcp add --transport http found-by-ai https://areyoufoundbyai.com/mcp/demo
```

Or add this URL to the Claude app (Settings, Connectors, Add custom connector), Cursor, or any
other MCP client as a remote server (Streamable HTTP). No key and no signup:

```
https://areyoufoundbyai.com/mcp/demo
```

The demo is connected to our own live monitoring of areyoufoundbyai.com, so you are
interrogating real production data. Ask your AI: "how visible is this business to AI, and what
would you fix first?"

## What your AI gets

Twenty tools: nineteen read tools over live measurements, plus one action. They are scoped to the
monitor behind the token, so none of them takes a URL:

- `get_visibility`: AI Visibility and AI Readiness scores (each out of 100) with the previous week, the separate off-site Footprint score, and the subscores
- `get_answers`: the answer each engine gave to each tracked buyer question, with the competitors it named and the web searches it ran first
- `get_question_trajectories`: question-by-question history across the engines
- `get_rivals` / `get_share_of_voice`: who AI names instead of you, and how often
- `get_cited_queries`: the questions where a given competitor gets named
- `get_mentions`: new pages on the web that mention the business, when a mention check has been run
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
- `request_rescan`: the one action, a fresh measurement capped by the plan's on-demand allowance (5 per rolling 7 days). On the demo it returns a worked example and queues nothing

## Customers

Every monitored site has its own token, on the Free plan as well as Pro. The recommended form is
the static endpoint with the token in a header, because URLs end up in server logs, proxies and
browser history and headers do not:

```bash
curl -X POST https://areyoufoundbyai.com/mcp \
  -H "authorization: Bearer <your-token>" \
  -H "content-type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

`x-api-key: <your-token>` works too, and the path form `https://areyoufoundbyai.com/mcp/<token>`
keeps working for anything already pointed at it. Agency keys get a separate network catalogue
over the sites they are allowed to see. Setup guide, with a one-click Cursor link and the Claude
Code command: [areyoufoundbyai.com/guides/connect-your-ai](https://areyoufoundbyai.com/guides/connect-your-ai)

The readiness method and the audit suite are open source at
[techhorizonlabs/thl-open](https://github.com/techhorizonlabs/thl-open). The measurement engine
itself is not.

## Registry manifest

[`server.json`](./server.json) is the manifest for the official MCP registry. Its `version` is the
version of this registry entry, not of the server software: the registry needs a new version
number each time the entry's metadata changes, so the entry is at 1.1.1 while the hosted server
reports 1.1.0 in its `serverInfo`. Both describe the same twenty tools.

Tech Horizon Labs, Noosa, Australia. hello@techhorizonlabs.com
