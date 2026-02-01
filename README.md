# rwa-stablecoin-risk-spark
RWA Stablecoin Solvency & Liquidity Stress Testing (Spark Case Study)

This project builds a small, reproducible risk framework to analyze solvency and liquidity risks in an RWA-backed stablecoin system, using Spark (Maker / Sky ecosystem) as a case study. The focus is on asset–liability management (ALM) under interest-rate shocks, asset valuation haircuts, and redemption-driven liquidity stress.

All analysis is based on public, reproducible data and simplified economic assumptions.

## Method Overview

Asset-side proxy

	•	Protocol-level TVL from DeFiLlama (Spark)
	•	Used as a transparent proxy for reserve assets

Notebook 01 — Data construction

	•	Pulls and cleans historical TVL data
	•	Produces an asset-side time series for downstream analysis

Notebook 02 — Solvency stress testing

	•	Infers liabilities from a target collateral ratio
	•	Applies simplified duration-based sensitivity to interest-rate shocks
	•	Evaluates post-shock collateral ratios across haircut scenarios

Notebook 03 — Liquidity stress testing

	•	Models redemption shocks and settlement delays
	•	Estimates cash availability vs. redemption demand
	•	Identifies liquidity shortfall regions via heatmaps

## Key Assumptions
	•	TVL is used as a proxy for reserve assets
	•	Liabilities are assumed to redeem at par
	•	Duration and liquidity parameters are simplified for clarity
	•	Results are illustrative, not predictive

All assumptions are explicit and can be refined in future extensions.

## Disclaimer

This project is for research and educational purposes only.
It does not constitute financial advice or an assessment of any live protocol.











