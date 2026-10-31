# Data lineage and methodology

| Stage | File | Input | Granularity | Row count | Disclosure |
|---|---|---|---|---:|---|
| 1 | September source Excel | Local `backend/signal_logs/2026-09-*/signals_*.xlsx` | raw signals | 323 | Private |
| 1 | October source Excel | Local `backend/signal_logs/2026-10-*/signals_*.xlsx` | raw signals | 267 | Private |
| 2 | Sep–Oct master | Above two monthly extracts | raw signals | 590 | Private |
| 3 | Clean private master | Raw master with traceability and quality flags | raw signals | 590 | Private |
| 4 | Safe signal workbook | Restricted columns removed from master | raw signal summary | 590 | Git-safe candidate |
| 1b | September PDF | Monthly backtest PDF | filtered outcomes | 266 | Private |
| 1b | October PDF | Monthly backtest PDF | filtered outcomes | 239 | Private |
| 5 | Sanitized Power BI reporting workbook | Signal logs reconciled with PDF-derived records | overlapping 505+590, **not additive** | 505 backtest + 590 raw | Git-safe candidate |
| 6 | Native Power BI project | Sanitized data + reporting measures | semantic model/report | 4 pages | Portfolio |

Source issue: Full daily Excel log files are retained in the local MarketEdge backend and **were not uploaded to this package**. Monthly extracts preserve source file/row references. 505 PDF results and 590 signal logs **must not be combined as separate trades**.

Quality: 6 incomplete core signal rows and 13 missing outcomes were reported in the extracted source. Repeat-key flags require individual review and are not confirmed duplicate executions. Backtest PDFs exclude some trades due to lot-size/data gaps. The final dashboard reports **gross** performance, not verified net earnings, and 2 months do not demonstrate live predictive edge.

Confidentiality: Exact option contract and timing identifiers, candidate reasons and proprietary scoring inputs stay outside the public/portfolio folder. Publishing even sanitized data should be approved by the data owner. 
