# MarketEdge | Trading Performance Intelligence — Power BI

**Data Analyst portfolio project | September–October 2026**

A four-page Power BI case study exploring historical trading-signal outcomes, segment performance, risk, and data reliability. Built with **Power BI Desktop, Power Query, DAX, and Excel**.

> **Scope:** Descriptive analysis of historical backtest reports. The figures are *reported gross outcomes*, **not independently verified live trading profits or a prediction of future returns**.

## Dashboard preview

| 01 — Executive Decision Center | 02 — Segment Intelligence |
|---|---|
| ![Executive Decision Center](screenshots/01-executive-overview.png) | ![Segment Intelligence](screenshots/02-sector-intelligence.png) |
| **03 — Exit & Risk Laboratory** | **04 — Evidence & Data Reliability** |
| ![Exit & Risk Laboratory](screenshots/03-target-risk.png) | ![Evidence & Data Reliability](screenshots/04-data-quality.png) |

## Business problem

How can historical signals and backtest reports be turned into an interpretable decision-support dashboard? The analysis asks:

- Which months, segments, grades, and exit types contributed to reported gross outcomes?
- How do win rate, profit factor, average risk-adjusted result and drawdown vary across cohorts?
- Which data-quality gaps make comparisons or conclusions less reliable?

## At-a-glance results

| Historical reporting metric | Value |
|---|---:|
| Filtered, PDF-derived backtest outcomes | **505** (266 September; 239 October) |
| Raw signal-log records | **590** (323 September; 267 October) |
| Reported backtest win rate | **63.8%** |
| Reported gross P&L | **₹12,28,034** |
| Reported profit factor | **2.32** |
| Average result | **≈ 0.56R** |
| Repeat-key review flags | **119** |
| Incomplete core records | **6** |

**Important:** The 505 backtest outcomes and 590 signal records describe overlapping populations. They are **not 1,095 independent trades**. Repeat-key flags are **not confirmed duplicate executions**. Brokerage, taxes, slippage and independently verified net profitability are not available.

## Dashboard pages

1. **Executive Decision Center** — Core KPIs, trend and contribution visualizations, month-level comparisons.
2. **Segment Intelligence** — Performance by trading cohort, sector, grade and contract-side categories.
3. **Exit & Risk Laboratory** — Exit mix, payoff distribution, historical drawdown and risk context.
4. **Evidence & Data Reliability** — Source coverage, missing records, repeat-key review flags and auditable cohort tables.

## Tools and analytical approach

- **Excel / Power Query:** source cleanup, typing and reporting-data preparation.
- **Power BI semantic model:** separate `FactBacktest` and `FactSignals` tables for distinct record types.
- **DAX:** filter-aware KPIs including win rate, gross P&L, profit factor, average R and quality indicators.
- **Data validation:** reconciling monthly summaries and identifying reporting limitations rather than hiding incomplete data.
- **Visualization and communication:** interactive dashboard with explicit warnings against interpreting gross backtest outcomes as verified profits.

## Reproduce the dashboard locally

This repository includes a native **Power BI Project (.pbip)**, its report/semantic-model directories, and sanitized reporting workbooks.

1. Install **Power BI Desktop** and clone this repository:
   ```powershell
   git clone https://github.com/dhanunjaya-kd/marketedge-powerbi-dashboard.git
   ```
2. Open [MarketEdge_Interview_Portfolio_Ready.pbip](PowerBI_Project/MarketEdge_Interview_Portfolio_Ready/MarketEdge_Interview_Portfolio_Ready.pbip) in Power BI Desktop.
3. If the initial load displays incomplete or empty tables, select **Home → Refresh** and allow the model to finish loading. The author verified that a fresh clone opened in Power BI Desktop and populated after refresh on their Windows PC.
4. Check all four report pages and slicer interactions. The screenshots show the expected reporting presentation.

**Portability note:** The fresh-clone opening and initial refresh were tested on one Windows installation. This is not a guarantee of compatibility across every Power BI Desktop version or machine. A Power BI service/live-hosted report link is not provided.

## Repository guide

| Folder/file | Contents |
|---|---|
| [`PowerBI_Project/`](PowerBI_Project/) | Native Power BI report and semantic model |
| [`Sanitized_Data/`](Sanitized_Data/) | Sanitized Excel reporting workbooks |
| [`PowerBI_Support/`](PowerBI_Support/) | Supporting DAX and theme references |
| [`Source_And_Methodology/`](Source_And_Methodology/) | Source index, lineage and limitations |
| [`screenshots/`](screenshots/) | Four exported dashboard page images |
| [`Presentation/`](Presentation/) | Additional design references |

**Data provenance:** See [data lineage and limitations](Source_And_Methodology/DATA_LINEAGE_AND_LIMITATIONS.md). The original broker/strategy source logs and proprietary signal-entry rules are excluded.

## Key analytical caveats

- The period covers **two months**; findings are descriptive, not evidence of a repeatable predictive edge.
- Gross historical P&L does **not** account for independently validated trading charges or slippage.
- Missing outcomes, incomplete rows, and repeated keys require audit before any stronger claims.
- Do not equate report outcomes with broker-confirmed live fills or realized earnings.

## Interview / resume description

**Power BI Trading Performance Analytics | Excel, Power Query, DAX**

Designed a four-page interactive Power BI dashboard to analyze **505 historical backtest outcomes** alongside **590 overlapping signal-log records**. Built cohort-level KPIs for reported gross P&L, win rate, profit factor and risk; documented data lineage, quality flags and limitations to support reproducible analysis.

---

*Independent analytics portfolio case study. No trading recommendation or guaranteed performance is implied.*
