# Interview walk-through (2 minutes)

**Business problem** — Understanding whether apparent historical F&O trading performance is consistent across market segments and exit outcomes, rather than presenting profit alone.

**Data engineering** — Integrated cleaned, sanitized September and October signal extracts with 505 filtered PDF backtest results and reviewed 590 raw log records. Kept two overlapping populations separate.

**Modeling** — Separate FactBacktest and FactSignals reporting tables; reusable DAX measures for count, win-rate, gross P&L, profit factor, average R, end-of-day drawdown, and sample-size flags.

**Analysis** — Segment matrix and bubble chart let viewers compare win-rate against payoff and the number of observations. Exit waterfall decomposes gross returns.

**Responsible caveats** — Results are reported gross backtest values, not broker-verified net profits. Two months is short, sample sizes can be small, and omitted contracts/duplicate candidates can bias results.

**Privacy** — Entry logic, scoring formulas, contract-level timestamps, strike rules and internal thresholds are not included.

# Suggested demonstration

1. Page 1: 505 gross historical outcomes. Filter SignalFamily to Sniper (non-Tape) for 419, Tape separately 86.
2. Page 2: Select one sector; read win rate, average R, and cohort size together.
3. Page 3: Show stop-loss contribution and that the drawdown is **end-of-day** only; no false precision.
4. Page 4: Explain why 505 and 590 are not additive and why 'repeat review' is not the same as confirmed duplicate execution.
