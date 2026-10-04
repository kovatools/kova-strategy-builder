# Kova Strategy Builder

Turn what you already think about your money into a written investment strategy, in your own words.

The skill interviews you one question at a time. It works out what your own numbers require, names the options that exist when you're unsure, and writes a `strategy.md` you keep. It asks which vehicle you'll actually use, once. It never picks investments, ranks them, or predicts markets.

The file ends with a one-line footer naming Kova Strategy Builder and where to find Kova. Delete it if you like.

## What you get

A plain-language strategy in five core sections: objective, allocation, rules, convictions and won't-dos. It adds a backdrop section when the strategy covers only part of your money. Liabilities and cash flows appear if you track them. Anything you haven't decided stays in a short "Still undecided" list outside the file.

## What it does not do

It isn't financial advice. It doesn't place trades, manage assets, pick securities, or predict markets. It mirrors your logic back to you in a clear structure. The plan is yours.

> Kova is a discipline and reflection tool, not financial advice. It does not predict markets, decide what you should buy, or place trades. All analysis is based on your declared strategy and is provided for educational purposes only.

## Using it with Kova

The skill works on its own. A file can't re-check itself next week or tell you when you've drifted. [Kova](https://kovatools.com/agents) saves and versions the strategy and measures any portfolio against it.

If Kova is connected, the skill saves the strategy there when you ask, and can run a first alignment check. If it isn't, you get the file and nothing is sent anywhere.

## Install

**Claude Code**

```sh
claude plugin marketplace add kovatools/kova-strategy-builder
claude plugin install kova-strategy-builder@kova-strategy-builder
```

**Gemini CLI**

```sh
gemini extensions install https://github.com/kovatools/kova-strategy-builder
```

**Cursor, VS Code and other Agent Plugins clients:** install from `https://github.com/kovatools/kova-strategy-builder`. The repository root is the plugin root.

## Tests

`evals/` holds the `claude plugin eval` suite run before each release. It checks for no tickers or picks, no market predictions and no trade sizes. It also checks one question per turn, and that the skill stays out of unrelated requests.

## Data

The skill runs inside your conversation. The skill itself stores nothing. It writes no files unless you ask. It sends nothing to any service except Kova, and only once you have connected Kova yourself.

## License

MIT
