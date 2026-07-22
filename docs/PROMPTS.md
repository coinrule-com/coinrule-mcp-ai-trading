# Coinrule MCP example prompts

Once Coinrule is connected, ask your AI assistant in plain language. It chooses the appropriate MCP tool for you.

> [!TIP]
> Add **“on paper”** or **“use paper trading”** to a launch prompt to try it without risking real funds.

Prompts marked **Read + Write** require both `coinrule:read` and `coinrule:write`. Read-only prompts work with `coinrule:read`.

## Check on your account

**Read only**

```text
Show my Coinrule bots and how each one is doing.
```

```text
Am I up or down today across all my strategies?
```

```text
How much USDT do I have on Binance?
```

```text
What are my current holdings across every exchange?
```

```text
Show the recent buy and sell signals from my bots.
```

```text
What has my BTC momentum bot done in the last 24 hours?
```

## Create and launch a strategy

**Read + Write**

```text
Create a bot that buys BTC when RSI(14) drops below 30 and sells when it rises above 70, on Binance.
```

```text
Set up a weekly DCA into ETH on paper trading.
```

```text
Make a trailing-stop strategy on SOL perps on Hyperliquid with 4% risk per trade.
```

```text
Turn this idea into a live bot: buy the dip 3% on BNB, take profit 6%.
```

## Use templates and baskets

**Read + Write** except where noted

```text
Show me the beginner strategy templates and launch the RSI one on paper.
```

```text
What baskets are available for crypto spot?
```

The preceding prompt is **Read only**. Launching or creating a basket needs Read + Write:

```text
Launch the layer-1 basket with $500 on paper trading.
```

```text
Build a custom basket of BTC, ETH, and SOL, equally weighted, rebalanced weekly, then launch it with $1,000.
```

## Backtest before you commit

Viewing saved backtests is **Read only**. Starting a backtest or comparing scenarios requires **Read + Write**.

```text
Backtest an RSI mean-reversion strategy on BTC/USDT, 1h, over the last year.
```

```text
Compare 2%, 4%, and 6% stop-loss variants of that strategy.
```

```text
Show me my saved backtests and summarize the best one.
```

## Manage running bots

**Read + Write**

```text
Pause my ETH grid bot but keep the positions open.
```

```text
Stop my losing SOL bot and close its positions.
```

```text
Resume the DCA bot I paused yesterday.
```

```text
Update my BTC bot to take profit at 8% instead of 6%.
```

## Get more reliable results

- Name the venue, such as Binance, Hyperliquid, Trading 212, or a paper venue, so Coinrule can route the request correctly.
- State the capital amount for strategy or basket launches, for example, “with $500.”
- Say whether you want paper or live trading.
- Ask the assistant to share the Coinrule dashboard link it receives after it creates or launches a strategy.
- Start with a read-only question or a paper-trading launch before granting access to real funds.

For every available capability and its required access level, see [TOOLS.md](TOOLS.md). For troubleshooting connection problems, see the [Coinrule MCP troubleshooting guide](https://cloud.coinrule.com/docs/mcp/troubleshooting).
