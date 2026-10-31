# MarketEdge — final interview walkthrough

## 45-second opening

> “I built a Power BI reporting layer from 505 historical backtest outcomes and 590 original signal-log records from September–October 2026. These populations overlap, so I kept them separate and reconciled the PDF outcomes to the underlying reporting data. I used DAX to calculate win rate, R-multiple, gross return, profit factor and end-of-day gross drawdown; included sample-size flags; and designed an interactive sector–grade analysis that does not reveal proprietary signal-generation methods. The results are backtested gross outcomes, not verified live or after-charge profitability.”

## Five-minute demo

1. **Decision Center**: Explain 505 reported outcomes, 322 positive (63.8%), ₹12,28,034 reported gross, profit factor ~2.32. Point out 'gross ≠ net', look at historical gross trajectory and exit-contribution chart. Use Top 5 sector ranking and filter context.
2. **Segment Intelligence**: Show how sector–grade matrix uses one cell containing Win% and sample size; demonstrate that 100% from n=2 cannot be interpreted like 70% from n=100. Hover sector–grade bubble: sector, grade, n, win%, avg R, gross contribution, PF and warning. Filters are descriptive and do not expose entry rules.
3. **Risk Laboratory**: Show why win rate is incomplete: winning and losing trade sizes, stop-loss contribution, payoff waterfall and end-of-day *gross* drawdown. Show final exits (SL, T1/T2/T3), not cumulative target touches. Explain why T1-only paper trading is not directly comparable to historical backtest exits without intratrade price paths.
4. **Evidence & Data Reliability**: Explain 590 raw logs vs 505 filtered backtest outcomes. 119 repeated-key flags are *review candidates*, not proven duplicate executions; 6 incomplete signal rows; expired/missing outcomes. Trace cohort aggregations by month, sector and grade without publishing strike/expiry/entry conditions.

## Five grounded observations

- September 2026: 266 reported outcomes, 167 wins, ₹4,87,304 gross.
- October 2026: 239 reported outcomes, 155 wins, ₹7,40,730 gross (includes 86 Tape Momentum outcomes).
- Two-month totals: 505 reported outcomes, 322 wins, ₹12,28,034 gross — no independently verified transaction costs.
- Excluding Tape Momentum, the dataset contains 419 non-Tape outcomes. Filtering from 'All' to 'Sniper' changes the basis for every metric.
- 590 raw signal-log records are an overlapping reporting population, not an extra 590 independent trades.

## What **not** to claim

- “My strategy produces 63.8% live win rate.” Historical, filtered backtests ≠ forward-tested trading.
- “I earned ₹12.28L.” Gross historical report figures are not verified brokerage income.
- “There are 119 duplicate trades.” There are 119 repeated-key *review flags*.
- “The model predicts the best sector.” These are descriptive retrospective comparisons from two months, and small sample rates may be unstable.
- “DAX calculates our secret entry signals.” Report model contains analytical outcomes, not underlying proprietary decision conditions.

## What an interviewer can inspect

- DAX ratios, filter context, `RANKX` Top 5 ranking, data-quality measures, EOD drawdown and cohort sample warnings.
- Intentional modeling choices: separate fact populations; gross vs net; original input partitions preserved.
- PBIR native visual definitions and four-page narrative: performance → drivers → risk → evidence.

## Pre-presentation mandatory test in Power BI Desktop

Open, refresh, and confirm 4 pages without errors. Inspect all four final exits with no scroll; test sector–grade bubble and tooltips; select a grade and a month; confirm dynamic evidence cards update; inspect missing data month table; check for clipped text at your actual monitor scale. Save a PBIX from Desktop only after that test. Hide editor panes and use Fit to width while presenting.
