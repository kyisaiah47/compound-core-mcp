# parserail-mcp

An [MCP](https://modelcontextprotocol.io) server for **[ParseRail](https://parserail.thecompound.tech)**, gives Claude, Cursor, and any Model Context Protocol client native tools to parse documents, extract fields, redact PII, analyze contracts, fight chargebacks, and enrich companies.

## Setup

Get a key at **[parserail.thecompound.tech](https://parserail.thecompound.tech)**. Add the server to your MCP client config. ParseRail has no free tier. Buy credits up front through a $20 pack or a plan from $19/mo. ParseRail charges a call only when it succeeds.

**Claude Code:**

```bash
claude mcp add parserail -e PARSERAIL_API_KEY=ksk_live_… -- npx -y parserail-mcp
```

**Claude Desktop / Cursor** (`mcpServers` config):

```json
{
  "mcpServers": {
    "parserail": {
      "command": "npx",
      "args": ["-y", "parserail-mcp"],
      "env": { "PARSERAIL_API_KEY": "ksk_live_…" }
    }
  }
}
```

## Tools

| Tool | What it does |
| --- | --- |
| `parserail_parse` | Document (invoice/EOB/COI, PDF/image/text) → structured JSON |
| `parserail_extract` | Pull named fields out of any text |
| `parserail_classify` | Label text against your taxonomy |
| `parserail_summarize` | Summary + key points + action items |
| `parserail_redact` | Strip PII/PHI from text |
| `parserail_sentiment` | Sentiment, aspects, and themes |
| `parserail_contract` | Contract → parties, terms, obligations, risk flags |
| `parserail_chargeback` | Dispute details → representment packet |
| `parserail_enrich` | Domain or email → company profile |
| `parserail_account` | Credit balance |

Documents can be passed as `fileUrl`, raw `text`, or `fileBase64` + `fileMimeType`.

## Pricing

You pay with pay-per-call credits. You do not need a subscription. ParseRail charges you only when a call succeeds. See [parserail.thecompound.tech/docs](https://parserail.thecompound.tech/docs).

MIT, Compound Labs
