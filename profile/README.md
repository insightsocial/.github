# InsightSocial

**Public data from nine social platforms. One account, one credit balance.**

InsightSocial collects public data from Instagram, TikTok, Facebook, LinkedIn, X (Twitter), Threads, YouTube, Reddit and Pinterest, and hands it to you as rows: posts, comments, profiles, followers and contact details. There are two ways in. A Chrome extension scrapes the pages you are already looking at, with no code. A REST API returns the same kinds of data to your scripts and AI agents. Both draw on the same credit balance.

## Start here

| You want to | Go to |
| --- | --- |
| Export data from a page you have open, no code | [Install the Chrome extension](https://chromewebstore.google.com/detail/free-social-scraper-expor/cddgiejchlkeedmhjeodlcjdiddlcdld) |
| Call the API from code | [Quickstart](https://www.insightsocial.app/docs/quickstart) |
| Set up your coding agent in one command (key, skill, MCP) | [CLI](https://github.com/insightsocial/cli): `npx -y insightsocial init` |
| Add the MCP server to any client | `npx -y insightsocial mcp` - [setup](https://github.com/insightsocial/cli#mcp-server-any-client) |
| Hand the API to Claude, Codex, Cursor or Gemini CLI | [Agent skills](https://github.com/insightsocial/skills): `npx skills add insightsocial/skills` |
| Wire the API into your own agent | [Using an AI agent](https://www.insightsocial.app/docs/ai-agents) |
| Generate a client or agent tools from OpenAPI | [OpenAPI spec](https://github.com/insightsocial/openapi), live at `api.insightsocial.app/v1/openapi.json` |
| Try an endpoint before writing code | [API Explorer](https://www.insightsocial.app/portal/api/explorer) |
| Read the facts: sources, limits, what is not supported | [FACTS.md](https://github.com/insightsocial/insightsocial/blob/main/FACTS.md) |

## The API

240+ GET endpoints over nine platforms. Every call uses the same `x-api-key` header and returns the same JSON envelope, so switching platforms means changing one path segment.

```bash
curl "https://api.insightsocial.app/v1/tiktok/profile?handle=nasa" \
  -H "x-api-key: $INSIGHTSOCIAL_API_KEY"
```

- **Priced per endpoint.** A profile lookup costs 20 credits. Metered endpoints, such as paginated comments, hold a ceiling and charge only what the call used.
- **Failed calls and empty results are free.** Every response reports `credits_used` and `credits_remaining`.
- **Free catalogue.** `GET https://api.insightsocial.app/v1/endpoints` lists every path, parameter and price. It needs no key, so an agent can plan a job and price it before it spends anything.

Full reference: [insightsocial.app/docs](https://www.insightsocial.app/docs)

## The Chrome extension

Open a supported page, such as a hashtag, a group, a profile or a post. The side panel recognizes what kind of page it is and collects it in your own browser session. Your password and cookies are never shared with us. Results land in the [web portal](https://www.insightsocial.app/portal/history), where you can filter them and export to Google Sheets, CSV, Excel or JSON.

## Pricing

Free to start, with no credit card. One balance covers both API calls and exported rows.

| | Free | Pro |
| --- | --- | --- |
| Credits / month | 500 | 10,000 |
| Price | $0 | $9.99/mo, or $7.99/mo billed yearly |

One-time packs never expire. See [insightsocial.app/pricing](https://www.insightsocial.app/pricing).

## Contact

- Website: [insightsocial.app](https://www.insightsocial.app)
- Support: [support@insightsocial.app](mailto:support@insightsocial.app)
- X: [@dovy_dev](https://x.com/dovy_dev)

<sub>InsightSocial is not affiliated with Meta, ByteDance, X Corp, Microsoft, Google, Reddit or Pinterest. Platform names are trademarks of their respective owners.</sub>
