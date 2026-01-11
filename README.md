# rwa-stablecoin-risk-spark
Risk and solvency stress testing for RWA-backed stablecoins using DeFi protocol data

This project builds a transparent and reproducible risk framework to analyze
the solvency and liquidity of an RWA-backed stablecoin system, using Spark
(Maker / Sky ecosystem) as a system-level case study.

The focus is on asset–liability management (ALM), interest-rate risk, and
redemption-driven liquidity stress — core risks for tokenized U.S. Treasury
and stablecoin protocols.


## Motivation

As real-world assets (RWAs), especially U.S. Treasuries, are increasingly used
to back on-chain stablecoins, protocol stability depends not only on total
asset value, but also on:

- Interest-rate sensitivity (duration risk)
- Asset haircuts and valuation shocks
- Redemption dynamics and settlement delays
- Capital buffer adequacy

This project aims to translate traditional ALM and stress-testing concepts
into a DeFi-native, on-chain context.

## Data Sources & Proxies

This analysis intentionally avoids proprietary dashboards and relies on fully
reproducible public data.

- **Asset-side proxy**
  - Protocol-level TVL from DefiLlama (Spark)
  - Used as a transparent proxy for system reserves
- **Liability-side**
  - Stablecoin total supply (assumed $1 par value)
- **Interest rates**
  - U.S. Treasury yields from FRED (DGS1)

All proxy assumptions are explicitly stated and can be refined in future work.


## Methodology

The framework is structured in three layers:

1. **Data ingestion**
   - Pull protocol TVL history
   - Fetch Treasury yields
   - Read stablecoin supply
2. **Solvency stress testing**
   - Duration-based price sensitivity
   - Interest-rate shock scenarios
   - Asset haircuts
   - Collateral Ratio (Assets / Liabilities)
3. **Liquidity stress testing**
   - Redemption shocks
   - Settlement lag assumptions (T+1 / T+2)
   - Cash shortfall and buffer analysis
  

rwa-stablecoin-risk-spark/
├── README.md
├── notebooks/

│   ├── 01_data_fetch.ipynb
│   ├── 02_solvency_stress.ipynb
│   └── 03_liquidity_stress.ipynb

├── data/
│   └── spark_assets_proxy.csv
└── figures/
├── spark_tvl_timeseries.png
├── collateral_ratio_curve.png
└── liquidity_shortfall_heatmap.png


## Disclaimer

This project is for research and educational purposes only.
It does not constitute financial advice or an assessment of any live protocol.











