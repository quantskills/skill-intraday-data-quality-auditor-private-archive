# Intraday Data Quality Auditor

Community-maintained QuantSkills package for deterministic checks on normalized intraday OHLCV bars.

## Quick start

```bash
python scripts/audit_bars.py --demo
python scripts/audit_bars.py --input your_data.csv --out report.json
```

The CSV must contain `symbol`, `trading_date`, `session`, `timestamp`, `open`, `high`, `low`, `close`, and `volume`. The report flags timestamp order, duplicates, gaps, invalid OHLC relationships, non-positive prices, negative volume, and trading-date mismatches. Legitimate prior-calendar-date futures night sessions must use an explicit `night`, `night_session`, `overnight`, or `night_*` label.

For PandaData acquisition, use the sibling [`skill-pandadata-api`](https://github.com/quantskills/skill-pandadata-api) and normalize its output before running this offline script. Minute bars are not tick trades or Level-2 order-book data.

## Validation and limits

See [validation/README.md](validation/README.md). A gap is evidence to investigate, not proof of a vendor error or exchange halt. This research tool does not modify source data, trade, or provide investment advice.

GPL-3.0-only. Community project; not an official QuantSkills verification result. Creator and maintainer: [adennng](https://github.com/adennng).
