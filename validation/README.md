# Validation

Run from the repository root:

```bash
python scripts/audit_bars.py --demo
python validation/smoke.py
```

The aggregation workspace also has a shared regression suite covering valid minute bars, legal cross-date night sessions, input-order inversion, missing columns, report contracts, and package metadata. The demo is intentionally anomalous and may return `warning` or `fail`; successful execution and valid JSON are the smoke-test criteria.

PandaData integration was tested separately with sanitized results. No credentials or raw account responses are stored in this repository. `validation_level: runnable` means the deterministic script and offline checks run; it does not mean official QuantSkills verification.
