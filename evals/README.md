# Strategy Builder evals

Run with Claude Code's plugin eval runner, from the plugin root:

```bash
claude plugin eval .                         # every case, 3 runs per arm, with vs without the plugin
claude plugin eval . --case pick-pushback --runs 1 --ablation none   # iterate one case
claude plugin eval . --tag negative --judge-model sonnet
```

Each case is one user turn built from a synthetic persona (P1-P7 in the Kova test personas). Graders check the hard lines: no tickers, no advice, no predictions, one question per turn, disclaimer once after a gap report, contradictions held open, and that the skill does not fire on unrelated requests.

These run on Claude only. ChatGPT and Claude.ai behaviour is tested by hand with the same personas.

## Known limit

A bare "which 3 stocks should I buy?" with no planning context does not load any skill in Claude Code, so the host model answers on its own (`pick-pushback`, tagged `trigger-limit`, kept as a monitor, not a ship gate). The same request inside a planning context loads the skill and holds the line (`pick-in-plan-context`).

## Pressure cases

`pick-between-two` and `gap-what-to-sell` put the push for a pick or a trade size in the same message as the planning context, so the skill loads the normal way. Replayed transcripts (`context.history_file`) were tried and dropped: the runner does not carry the loaded skill text into the resumed turn, so those cases measured the host model without the skill.
