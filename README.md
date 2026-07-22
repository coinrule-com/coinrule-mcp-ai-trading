# Coinrule MCP

[![License: MIT](https://img.shields.io/badge/License-MIT-1F6FEB?style=flat-square)](LICENSE)
[![MCP: Streamable HTTP](https://img.shields.io/badge/MCP-Streamable_HTTP-5A45FF?style=flat-square)](https://modelcontextprotocol.io/)
[![OAuth 2.1](https://img.shields.io/badge/Auth-OAuth_2.1-0A7B83?style=flat-square)](https://cloud.coinrule.com/docs/mcp/connecting-your-ai-assistant)
[![Works with Claude, ChatGPT, and Grok](https://img.shields.io/badge/Works_with-Claude_%7C_ChatGPT_%7C_Grok-111827?style=flat-square)](https://cloud.coinrule.com/docs/mcp)

Connect your Coinrule account to an AI assistant and trade, monitor your portfolio, build strategies, run backtests, and launch baskets by chat.

Coinrule MCP is a hosted [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server. There is nothing to install locally: add the server URL to a compatible AI assistant, sign in once with Coinrule, and start chatting.

> [!WARNING]
> A Read + Write connection can launch strategies that trade real funds. Start with Read only or paper trading, review every request, and make the venue and capital amount explicit.

## Connect in under a minute

1. Choose a compatible client such as Claude, ChatGPT, Grok, Cursor, or VS Code.
2. Add this remote MCP server:

   ```text
   https://cloud.coinrule.com/mcp
   ```

3. Sign in to Coinrule when your client opens the OAuth window.
4. Choose **Read only** or **Read + Write**, then try:

   ```text
   Show my Coinrule bots and how each one is doing.
   ```

You need a [Coinrule Cloud account](https://cloud.coinrule.com/) and an AI client that supports remote MCP connectors with OAuth. Connect an exchange or broker to trade live, or use paper trading without one.

## Add Coinrule to your client

[![Add to Cursor](https://img.shields.io/badge/Cursor-Add_Coinrule-000000?style=for-the-badge)](cursor://anysphere.cursor-deeplink/mcp/install?name=coinrule&config=eyJ1cmwiOiJodHRwczovL2Nsb3VkLmNvaW5ydWxlLmNvbS9tY3AifQ==)
[![Add to VS Code](https://img.shields.io/badge/VS_Code-Add_Coinrule-007ACC?style=for-the-badge)](vscode:mcp/install?%7B%22name%22%3A%22coinrule%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fcloud.coinrule.com%2Fmcp%22%7D)

| Client | How to connect | Help |
| --- | --- | --- |
| **Cursor** | Use the button above, or add the remote server from [`examples/cursor-mcp.json`](examples/cursor-mcp.json). | [Cursor configuration](https://cursor.com/docs/mcp) |
| **VS Code** | Use the button above, or add the server to `.vscode/mcp.json` from [`examples/vscode-mcp.json`](examples/vscode-mcp.json). | [VS Code configuration](https://code.visualstudio.com/docs/agents/reference/mcp-configuration) |
| **Claude** | In Claude's connector settings, add a remote MCP connector and paste the server URL. | [Connect Claude](https://cloud.coinrule.com/docs/mcp/connect-claude) |
| **ChatGPT** | Go to **Settings → Apps / Connectors**, add a custom connector, and paste the server URL. | [Connect ChatGPT](https://cloud.coinrule.com/docs/mcp/connect-chatgpt) |
| **Grok** | In a Grok client with remote MCP support, add a custom tool or remote MCP server and paste the URL. | [Connect Grok](https://cloud.coinrule.com/docs/mcp/connect-grok) |
| **Another MCP client** | Use the client’s remote-MCP configuration and adapt [`examples/mcp-generic.json`](examples/mcp-generic.json) if it uses an `mcpServers` map. | [General connection guide](https://cloud.coinrule.com/docs/mcp/connecting-your-ai-assistant) |

OAuth starts when the client first connects. Do not add a Coinrule password or exchange API key to an MCP configuration file.

**ChatGPT `invalid_client`?** Remove the Coinrule connector and add it again from scratch. This refreshes the client registration. See the [ChatGPT guide](https://cloud.coinrule.com/docs/mcp/connect-chatgpt) or [troubleshooting](https://cloud.coinrule.com/docs/mcp/troubleshooting).

## You control the access

| Access level | OAuth scope | Your assistant can do |
| --- | --- | --- |
| **Read only** | `coinrule:read` | Inspect strategies, balances, holdings, trades, signals, PnL, and saved backtests. It cannot place or change trades. |
| **Read + Write** | `coinrule:read` + `coinrule:write` | Everything in Read only, plus create, launch, update, start, and stop strategies; launch baskets; and run backtests. |

Coinrule uses OAuth 2.1, so your assistant never receives your Coinrule password or exchange API keys. Review or revoke any connected assistant at [Settings → Integrations](https://cloud.coinrule.com/settings/integrations) at any time.

## What you can ask Coinrule to do

| Capability | Examples |
| --- | --- |
| **Monitor strategies** | List bots, inspect positions and triggers, view activity, trades, and PnL. |
| **Understand your portfolio** | Read balances, holdings, connected accounts, and recent buy/sell signals. |
| **Create and control strategies** | Validate an idea, create a strategy from plain English, then update, start, stop, or pause it. |
| **Use templates and baskets** | Browse strategy templates, build a custom basket, or launch a curated basket. |
| **Test ideas** | Run historical backtests, compare scenarios, and review saved results. |

See the complete, scope-marked [tools reference](docs/TOOLS.md).

## Prompts to try

**Read only**

```text
What are my current holdings across every exchange?
```

```text
What has my BTC momentum bot done in the last 24 hours?
```

**Read + Write**

```text
Set up a weekly DCA into ETH on paper trading.
```

```text
Backtest an RSI mean-reversion strategy on BTC/USDT, 1h, over the last year.
```

```text
Build a custom basket of BTC, ETH, and SOL, equally weighted, then launch it with $1,000 on paper trading.
```

Find more copy-paste examples in [docs/PROMPTS.md](docs/PROMPTS.md).

## Supported venues and assets

Use Coinrule MCP with the accounts you have connected to Coinrule, including:

- Binance
- Coinbase
- Kraken (spot and perpetuals)
- Hyperliquid
- KuCoin
- Trading 212

Supported asset types include crypto spot, perpetuals, and stocks, with paper-trading equivalents. See [exchanges and connections](https://cloud.coinrule.com/docs/exchanges) for current venue support and setup instructions.

## Distribution

This repository contains a standards-based [`server.json`](server.json) manifest for the hosted Streamable HTTP server. It is ready to support publication in the [official MCP Registry](https://modelcontextprotocol.io/registry/about); registry publishing and namespace verification are separate release steps.

## Resources

- [Coinrule MCP overview](https://coinrule.com/mcp/)
- [MCP documentation](https://cloud.coinrule.com/docs/mcp)
- [Connection guide](https://cloud.coinrule.com/docs/mcp/connecting-your-ai-assistant)
- [Tools reference](https://cloud.coinrule.com/docs/mcp/tools-reference)
- [Example prompts](https://cloud.coinrule.com/docs/mcp/example-prompts)
- [Pricing](https://cloud.coinrule.com/pricing)
- [Support](https://cloud.coinrule.com/support)

This repository and the Coinrule MCP are provided by [Coinrule](https://coinrule.com/), AI-powered trading automation backed by Y Combinator.

Trading involves risk. Nothing in this repository or in an AI assistant's response is financial, investment, or trading advice.
