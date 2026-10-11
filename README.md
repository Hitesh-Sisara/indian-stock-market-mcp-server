# Indian Stock Market MCP Server (Python)

**An Indian stock market MCP server that gives Claude, ChatGPT, Cursor, VS Code, Codex, Gemini CLI and other AI agents live data on every NSE and BSE stock: share prices, Nifty 50 and Sensex, company fundamentals, a stock screener, FII/DII flows, option chains and more.**

[![PyPI](https://img.shields.io/pypi/v/tapetide-mcp?label=pypi%20tapetide-mcp)](https://pypi.org/project/tapetide-mcp/)
[![npm](https://img.shields.io/npm/v/tapetide-mcp?label=npm%20tapetide-mcp)](https://www.npmjs.com/package/tapetide-mcp)
[![MCP Registry](https://img.shields.io/badge/MCP%20Registry-com.tapetide%2Fstock--research--mcp-blue)](https://registry.modelcontextprotocol.io/v0/servers?search=com.tapetide/stock-research-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![MCP](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)

Ask your AI assistant things like *"What's the Reliance share price today?"*, *"Show the Nifty 50 PE ratio vs its 10-year average"*, or *"Find small-cap stocks with ROE above 20% and low debt"* and get answers from real market data instead of stale training data.

**55 tools** · **8,200+ NSE/BSE stocks** · **free tier** · [setup guides for 16 clients](https://tapetide.com/mcp)

The server is powered by [Tapetide](https://tapetide.com/mcp) and runs on the official [`tapetide-mcp`](https://pypi.org/project/tapetide-mcp/) Python package.

## Quick start

1. Get a free API token at [tapetide.com/settings/tokens](https://tapetide.com/settings/tokens).
2. Add this to your MCP client config (Claude Desktop, Cursor, Windsurf, VS Code, Kiro, Zed...):

```json
{
  "mcpServers": {
    "indian-stock-market": {
      "command": "uvx",
      "args": ["tapetide-mcp"],
      "env": { "TAPETIDE_TOKEN": "your_token_here" }
    }
  }
}
```

Claude Code:

```bash
claude mcp add indian-stock-market -e TAPETIDE_TOKEN=your_token_here -- uvx tapetide-mcp
```

Prefer pip? `pip install tapetide-mcp`, then use `"command": "tapetide-mcp"`.
Prefer Node.js? `npx -y tapetide-mcp` works the same way.
Using claude.ai, ChatGPT, Gemini or Grok in the browser? Add `https://mcp.tapetide.com/mcp` as a custom connector. No install or token needed, you just sign in with Google.

### Run from this repo

```bash
uvx --from git+https://github.com/Hitesh-Sisara/indian-stock-market-mcp-server indian-stock-market-mcp-server
```

## Works with

Step-by-step setup guides for every major MCP client:

| Chat apps | Code editors & IDEs | Terminal agents |
|---|---|---|
| [Claude.ai](https://tapetide.com/mcp/claude-ai) | [Cursor](https://tapetide.com/mcp/cursor) | [Claude Code](https://tapetide.com/mcp/claude-code) |
| [ChatGPT](https://tapetide.com/mcp/chatgpt) | [VS Code (GitHub Copilot)](https://tapetide.com/mcp/vscode) | [Codex CLI](https://tapetide.com/mcp/codex) |
| [Claude Desktop](https://tapetide.com/mcp/claude-desktop) | [Windsurf](https://tapetide.com/mcp/windsurf) | [Gemini CLI](https://tapetide.com/mcp/gemini-cli) |
| [Grok](https://tapetide.com/mcp/grok) | [Kiro](https://tapetide.com/mcp/kiro) | [OpenCode](https://tapetide.com/mcp/opencode) |
| | [Zed](https://tapetide.com/mcp/zed) | [Command Code](https://tapetide.com/mcp/commandcode) |
| | [Cline](https://tapetide.com/mcp/cline) | |
| | [Antigravity](https://tapetide.com/mcp/antigravity) | |

Any other client that speaks the Model Context Protocol works too, over remote HTTP or local stdio.

## What you can ask

| Use case | Example prompt |
|---|---|
| Live NSE / BSE share price | "What's the HDFC Bank share price and 52-week range?" |
| Nifty 50 / Sensex / sector indices | "Which sector index performed best last month?" |
| Fundamental analysis | "Show TCS quarterly revenue, margins and cash flow for the last 8 quarters" |
| Stock screener | "Mid-caps with PE under 20, ROCE above 18% and rising promoter holding" |
| Technical analysis | "Stocks where RSI is below 30 and price is above the 200-day moving average" |
| FII / DII activity | "How much did FIIs sell in Indian equities this week?" |
| F&O and options | "NIFTY option chain near the money, with max pain and PCR" |
| IPOs, bulk and block deals | "Upcoming IPOs and today's bulk deals above ₹50 crore" |
| Annual reports and concalls | "Summarise guidance from Infosys's latest earnings call" |
| Portfolio and watchlist | "Track my holdings and show the day's P&L" |

## Coverage

- About 8,200 NSE and BSE listed stocks, including SME
- Daily OHLCV price history with delivery %
- Quarterly and annual P&L, balance sheet, cash flow and 326 screener ratios
- RSI, MACD, moving averages, Bollinger Bands, Supertrend and candlestick patterns
- Shareholding patterns, mutual fund holdings, analyst ratings and forecasts
- FII/DII cash flows, F&O participant OI, FPI sector allocation
- Index option chains with IV and Greeks, IV rank for about 556 underlyings, India VIX
- Corporate actions, news, and parsed filings (annual reports, concall transcripts)

55 tools in total. The full catalog is in the [official docs](https://tapetide.com/mcp).

## Who it's for

- Retail investors who want an AI research assistant for Indian stocks
- Developers building trading bots, AI agents or LangChain / LlamaIndex apps on Indian market data
- Analysts who want quick answers on NSE and BSE stocks without writing scrapers or juggling APIs

## FAQ

**Is it free?** Yes. The free plan includes 50 tool calls a day and 1,000 a month. See [tapetide.com/pricing](https://tapetide.com/pricing) for higher limits.

**Is the data real-time?** Quotes are live during market hours. Fundamentals, flows and filings update as they are published.

**Does it work offline or without an account?** No. The server fetches data from Tapetide's remote MCP endpoint, so you need an internet connection and a free token.

## Related

- Official Python package: [Tapetide-hq/nse-bse-indian-stock-market-data-mcp-python](https://github.com/Tapetide-hq/nse-bse-indian-stock-market-data-mcp-python)
- Official Node.js package: [Tapetide-hq/nse-bse-indian-stock-market-data-mcp](https://github.com/Tapetide-hq/nse-bse-indian-stock-market-data-mcp)
- Docs and setup guides: [tapetide.com/mcp](https://tapetide.com/mcp)

## License

MIT
