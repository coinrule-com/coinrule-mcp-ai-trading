# Coinrule MCP tools

Your AI assistant selects these tools from natural-language requests. You do not need to call them directly.

| Access | Required scope |
| --- | --- |
| **Read** | `coinrule:read` |
| **Write** | `coinrule:write` (granted together with `coinrule:read` as Read + Write access) |

The tools visible to your assistant depend on the access level you approve. For a guide to choosing an access level, see [Connect in under a minute](../README.md#connect-in-under-a-minute). The authoritative online reference is the [Coinrule MCP tools reference](https://cloud.coinrule.com/docs/mcp/tools-reference).

## Strategies: inspect

| Tool | Access | What it does |
| --- | --- | --- |
| `list_strategies` | Read | Lists all of your trading bots and strategies. |
| `get_strategy` | Read | Returns the full configuration and metadata for one strategy, including its dashboard link. |
| `get_strategy_status` | Read | Returns a live snapshot with open positions, PnL, paper balance, and trigger proximity. |
| `get_strategy_activity` | Read | Returns the event log for one strategy, including signals, lifecycle events, and evaluations. |
| `get_strategy_trades` | Read | Returns filled trades and closed positions for one strategy. |
| `get_strategy_pnl` | Read | Returns PnL time-series data for charting. |
| `get_strategy_feed` | Read | Returns a combined activity feed across all strategies. |

## Portfolio and accounts

| Tool | Access | What it does |
| --- | --- | --- |
| `get_portfolio_balances` | Read | Returns cash and quote balances on connected exchanges plus strategy allocations. |
| `get_portfolio_holdings` | Read | Returns asset holdings, total portfolio value, and allocation. |
| `get_recent_signals` | Read | Returns recent buy and sell signals across your bots. |
| `list_exchange_accounts` | Read | Lists connected exchange and broker accounts, including the venue and account IDs needed to launch live strategies. |

## Create and control strategies

All tools in this group require Write access.

| Tool | Access | What it does |
| --- | --- | --- |
| `validate_strategy` | Write | Parses a prompt or script and generates tests as the first step of a two-step launch. |
| `create_strategy` | Write | Launches a validated strategy on a chosen venue. |
| `create_strategy_from_prompt` | Write | Turns a plain-English request into a validated, tested, and launched strategy in one step. |
| `update_strategy` | Write | Changes a strategy configuration and redeploys it. |
| `start_strategy` | Write | Resumes a stopped strategy. |
| `stop_strategy` | Write | Stops or pauses a strategy, optionally closing open positions. |

## Templates

| Tool | Access | What it does |
| --- | --- | --- |
| `list_strategy_templates` | Read | Browses pre-built strategy scripts, including RSI, DCA, TradingView, and basket templates, filterable by level. |

## Baskets

| Tool | Access | What it does |
| --- | --- | --- |
| `list_baskets` | Read | Lists curated baskets and your custom baskets, filterable by category. |
| `list_basket_assets` | Read | Searches the asset universe when building a custom basket. |
| `create_basket` | Write | Defines a custom basket with 2–20 assets and target weights. |
| `launch_basket` | Write | Launches a curated or custom basket on one venue or across multiple venues. |

When a basket spans several exchanges, Coinrule maps each leg to a matching connected account. Connect every required venue before launching.

## Backtests

| Tool | Access | What it does |
| --- | --- | --- |
| `list_backtests` | Read | Lists your saved backtest runs. |
| `get_backtest` | Read | Returns the summary for one backtest run. |
| `get_backtest_export` | Read | Returns raw trades or export data for one backtest run. |
| `run_backtest` | Write | Runs one historical simulation. |
| `run_backtest_scenarios` | Write | Compares multiple parameter sets in one pass. |

## Supported venues and assets

Tools operate on the Coinrule accounts you have connected. Current documented venues include Binance, Coinbase, Kraken (spot and perpetuals), Hyperliquid, KuCoin, and Trading 212, across crypto spot, perpetuals, stocks, and paper-trading equivalents.

See [exchanges and connections](https://cloud.coinrule.com/docs/exchanges) for setup and current availability.
