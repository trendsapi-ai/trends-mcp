# Trends MCP - trend data MCP server for Claude, Cursor, VS Code & ChatGPT

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE) [![API v1](https://img.shields.io/badge/API-v1-blue.svg)](https://trendsapi.ai) [![MCP compatible](https://img.shields.io/badge/MCP-compatible-blueviolet.svg)](https://modelcontextprotocol.io) [![Free tier](https://img.shields.io/badge/free%20tier-100%20req%2Fmo-orange.svg)](https://trendsapi.ai/#pricing)

> **The Trends API MCP server.** Query Google, TikTok, Amazon, Reddit, YouTube, Steam, npm and 30+ trend sources in natural language from any MCP-compatible AI. Same data, same API key, no local install - it is a hosted remote server.

**Get a free API key (100 req/mo):** [https://trendsapi.ai/#get-key](https://trendsapi.ai/#get-key) · **REST docs:** [https://trendsapi.ai/#quickstart](https://trendsapi.ai/#quickstart)

---

## Connect in 30 seconds

The same API key powers the Trends API MCP server, so Claude, Cursor, VS Code, ChatGPT and any MCP-compatible client can query this data in natural language.

[**+ Add to Cursor (one click)**](cursor://anysphere.cursor-deeplink/mcp/install?name=trendsapi&config=eyJ1cmwiOiAiaHR0cHM6Ly9hcGkudHJlbmRzYXBpLmFpL21jcCIsICJoZWFkZXJzIjogeyJBdXRob3JpemF0aW9uIjogIkJlYXJlciBZT1VSX0FQSV9LRVkifX0=)

**Cursor / Windsurf / Cline** (`~/.cursor/mcp.json` or equivalent):

```json
{
  "mcpServers": {
    "trendsapi": {
      "url": "https://api.trendsapi.ai/mcp",
      "transport": "http",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**VS Code / GitHub Copilot** (`.vscode/mcp.json`):

```json
{
  "servers": {
    "trendsapi": {
      "type": "http",
      "url": "https://api.trendsapi.ai/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**Claude Desktop** (`claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "trendsapi": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://api.trendsapi.ai/mcp", "--header", "Authorization:${AUTH_HEADER}"],
      "env": { "AUTH_HEADER": "Bearer YOUR_API_KEY" }
    }
  }
}
```

**Claude.ai (browser):** Settings -> Connectors -> Add custom connector -> `https://api.trendsapi.ai/mcp`

Then ask things like:

```
How did "creatine gummies" grow on TikTok vs Google over the last 12 months?
What is trending on YouTube right now?
```

## What you can ask

```
Is "heatless curls" still growing on TikTok, or did it peak?
Compare 12-month growth of "creatine gummies" on Amazon vs Google.
What is trending on YouTube right now?
Which npm packages in the React ecosystem are gaining downloads fastest?
```

## Tools

| Tool | What it does | Needs a keyword? |
|---|---|---|
| `get_time_series` | Historical trend series for a keyword on one of 15 sources | yes |
| `get_growth` | Growth % over 3M / 6M / 12M / 5Y windows | yes |
| `get_top_trends` | 21 live trending feeds (Google, TikTok, YouTube, X, Reddit, Amazon, Steam, Spotify...) | no |

## Coverage

| Source | `source` value | What it measures |
|---|---|---|
| Google Search | `google search` | Search volume |
| Google Images | `google images` | Image search volume |
| Google News | `google news` | News search volume |
| Google Shopping | `google shopping` | Shopping search volume |
| YouTube | `youtube` | Search volume |
| TikTok | `tiktok` | Hashtag volume |
| Reddit | `reddit` | Subreddit subscribers |
| Amazon | `amazon` | Product search volume |
| Wikipedia | `wikipedia` | Page views |
| News volume | `news volume` | Article mention volume |
| News sentiment | `news sentiment` | Positive / negative score |
| App downloads | `app downloads` | Android downloads (AppBrain) |
| App rankings | `app rankings` | Android chart position |
| npm | `npm` | Weekly package downloads |
| Steam | `steam` | Concurrent players (monthly) |

### Live feeds

| Feed | `type` value |
|---|---|
| Google Trends | `Google Trends` |
| Google News Top News | `Google News Top News` |
| TikTok Trending Hashtags | `TikTok Trending Hashtags` |
| TikTok Trending Searches | `TikTok Trending Searches` |
| TikTok Shop Hot Products | `TikTok Shop Hot Products` |
| YouTube Trending | `YouTube Trending` |
| X (Twitter) Trending | `X (Twitter) Trending` |
| Reddit Hot Posts | `Reddit Hot Posts` |
| Reddit World News | `Reddit World News` |
| Wikipedia Trending | `Wikipedia Trending` |
| Amazon Best Sellers Top Rated | `Amazon Best Sellers Top Rated` |
| Amazon Best Sellers by Category | `Amazon Best Sellers by Category` |
| App Store Top Free | `App Store Top Free` |
| App Store Top Paid | `App Store Top Paid` |
| Google Play | `Google Play` |
| Top Websites | `Top Websites` |
| Spotify Top Podcasts | `Spotify Top Podcasts` |
| Steam Most Played | `Steam Most Played` |
| GitHub Trending Repos | `GitHub Trending Repos` |
| IMDb MOVIEmeter | `IMDb MOVIEmeter` |
| Open Library Trending Books | `Open Library Trending Books` |

## How it works

This is a **remote** MCP server hosted at `https://api.trendsapi.ai/mcp`. There is nothing to run locally and nothing to update. Your API key goes in the `Authorization` header; every MCP client above handles it natively or through `mcp-remote`.

Prefer raw REST? The same key works on `POST https://api.trendsapi.ai/api` - see the [main repo](https://github.com/trendsapi/trendsapi).

---

## Links

- **Docs & quickstart:** [https://trendsapi.ai/#quickstart](https://trendsapi.ai/#quickstart)
- **llms.txt (machine-readable API reference):** [https://trendsapi.ai/llms.txt](https://trendsapi.ai/llms.txt)
- **Pricing (free tier: 100 requests/month):** [https://trendsapi.ai/#pricing](https://trendsapi.ai/#pricing)
- **Get an API key:** [https://trendsapi.ai/#get-key](https://trendsapi.ai/#get-key)

## License

MIT - see [LICENSE](LICENSE). Data is served by [Trends API](https://trendsapi.ai); usage of the API itself is subject to the plan limits on your key.
