# DCF Model Demo

[![Demo Smoke Test](https://github.com/gilhermanns/dcf-model-demo/actions/workflows/smoke.yml/badge.svg)](https://github.com/gilhermanns/dcf-model-demo/actions/workflows/smoke.yml)

An export-oriented demonstration built around the [`modern-automated-dcf`](https://github.com/gilhermanns/modern-automated-dcf) package. The repository contains versioned Excel workbooks that show the structure of a multi-company DCF output and a small command-line wrapper for regenerating them when market data is available.

## Included review artefacts

| File | Purpose |
|---|---|
| [`outputs/AAPL_DCF_Model.xlsx`](outputs/AAPL_DCF_Model.xlsx) | Example single-company DCF workbook structure |
| [`outputs/MSFT_DCF_Model.xlsx`](outputs/MSFT_DCF_Model.xlsx) | Example single-company DCF workbook structure |
| [`outputs/TSLA_DCF_Model.xlsx`](outputs/TSLA_DCF_Model.xlsx) | Example single-company DCF workbook structure |
| [`outputs/Master_Comparison.xlsx`](outputs/Master_Comparison.xlsx) | Consolidated output layout across the generated workbooks |

The workbooks are demonstration artefacts, not current valuations or price targets. Their contents depend on the retrieval date and the explicit model assumptions used when they were generated.

## Run locally

```bash
git clone https://github.com/gilhermanns/dcf-model-demo.git
cd dcf-model-demo
python -m pip install -r requirements.txt
python run_demo.py --help
```

To regenerate workbooks, run the selected ticker set:

```bash
python run_demo.py --tickers AAPL,MSFT
```

The demo depends on the published `modern-automated-dcf` package declared in `requirements.txt`; no local path dependency is required.

## Validation

GitHub Actions performs a smoke check on every push and pull request. It installs the declared dependencies, compiles `run_demo.py` and verifies the CLI help path. This is intentionally a lightweight interface check; a full workbook regeneration relies on external market-data availability.

## Limitations

- DCF results depend on public data availability and model assumptions.
- The workbooks are analytical examples, not investment recommendations or audited financial models.

---

*Entwickelt mit Unterstützung von Claude Code (Anthropic).*
*For research and educational purposes; not investment advice.*
