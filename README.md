# Hi, I'm Freeman 👋
### Blockchain Data Engineer 

I build **production-grade data pipelines for blockchain data**  from raw EVM logs to analyst-ready dataset. My work sits at the intersection of data engineering and DeFi: decoding ABI events at scale, modeling protocol behavior  and building forensic tools that make blockchain data legible.

I write about the architectures I build → **[Substack](https://freemandaily.substack.com)** · **[Twitter / X](https://x.com/freemandayly)**

---

## 🛠 Core Stack

**Ingestion & Processing** : PySpark · Apache Airflow · Kestra · Envio HyperIndex  
**Storage & Warehousing** : GCS · S3 · BigQuery · DuckDB · PostgreSQL · TimescaleDB  
**Transformation** : dbt (BigQuery · DuckDB · Athena adapters) · Medallion Architecture  
**Cloud**: AWS (EMR · Athena · Glue · S3) · GCP (Dataproc · BigQuery · GCS) · Terraform 
**APIs & Frontend** : FastAPI · React · HTML5 Canvas · Docker  

---

## 🔭 Featured Projects

### [Cross-Chain Fund & Bridge Analytics Pipeline](https://github.com/Freemandaily/cross-chain-flow)
**Multi-protocol bridge reconciliation pipeline**

A dbt + BigQuery pipeline that reconciles cross-chain token deposits and fulfillments into a single, normalized transaction ledger. Reads raw event logs directly from Google's public blockchain datasets across Ethereum, Arbitrum, Optimism, Avalanche, and Polygon, then correlates deposit and fill events for **Across V3, deBridge DLN, Stargate V2, Mayan Swift, and Wormhole** through a protocol-agnostic Medallion architecture (base → protocol → unified → enriched). Tracks per-transaction settlement latency (`time_to_fill_seconds`) and live `PENDING`/`COMPLETED` order status, with token metadata enrichment via the DefiLlama API and daily orchestration through Apache Airflow.

---

### [Ethereum DeFi Observatory](https://github.com/Freemandaily/ethereum-defi-observatory)
**End-to-end crash analysis pipeline**

> *$19 billion liquidated. 1.6 million traders wiped out. What did the Ethereum blockchain look like from the inside?*

Full GCP pipeline analyzing the October 10, 2025 crypto crash using raw on-chain data. PySpark reads from the Google Cloud Public Blockchain dataset via Dataproc, lands Parquet files in GCS, dbt transforms through staging → intermediate → marts, and Kestra orchestrates the full flow. Infrastructure provisioned with Terraform.

📊 [Live Looker Studio Dashboard](https://lookerstudio.google.com/u/2/reporting/d769e0bb-0d54-4e01-8e62-f2249adc214f/page/ysasF)

---

### [Blockchain Data Decoder](https://github.com/Freemandaily/Blockchain-data-decoder)
**Multi-protocol EVM log decoder**

High-performance PySpark batch pipeline that reads raw Ethereum event logs from the AWS public blockchain dataset and decodes them into structured DeFi event tables. Covers **Aave V1/V2/V3**, **Compound V1/V2/V3**, and **Morpho V1**  deposit, withdraw, borrow, repay, and liquidation events  through a unified, protocol-agnostic decoder architecture. Deployable locally or on AWS EMR.

---

### [TradesLens](https://github.com/Freemandaily/TradesLens)
**Multi-chain DEX terminal**

Real-time swap intelligence platform indexing **Uniswap V3**, **SushiSwap V3**, and **Solidly V3** across Ethereum Mainnet, Arbitrum, and Optimism. Envio HyperIndex handles multi-chain event ingestion; dbt models normalize heterogeneous protocol schemas into a unified `fct_dex_swaps` fact table via Medallion architecture; FastAPI serves analytical queries on top of TimescaleDB.

🔗 [Live Dashboard](https://intel-tradeslens.onrender.com/)

---

### [ChainTrace Forensic](https://github.com/Freemandaily/ChainTrace-Forensic)
**On-chain forensics tool**

Arkham-style forensic platform tracing the Kelp DAO exploit fund flow. PySpark batch pipeline joins ETH transfer events with transaction calls to identify Thorchain laundering routes. A graph transformation layer classifies wallets (Attacker / Hop / Exit) and outputs a topology JSON consumed by an interactive React + Canvas frontend with time-travel simulation.

---

### [Token Intelligence](https://github.com/Freemandaily/Token-Intelligence)
**Serverless analytics platform**

Demonstrates a local-first / serverless analytics stack with zero infrastructure overhead. Data stored as Parquet, queried directly by DuckDB's vectorized engine, transformed by dbt-duckdb, and served via FastAPI  with the entire database bundled as a single `.duckdb` file in a Docker container.

---

### [Blockchain Data Pipelines](https://github.com/Freemandaily/Data-Pipelines)
**ETL vs ELT architecture comparison · Python · Ethereum**

Side-by-side implementation of ETL and ELT architectures for processing Ethereum data, designed as a practical reference for understanding the tradeoffs between the two patterns.

---

## ✍️ Writing

I write deep technical articles on blockchain data engineering architecture breakdowns, protocol decoding, and pipeline design.

- **[ETL Pipeline for Blockchain Data Engineering](https://substack.com/@freemandaily/note/p-203373935?r=95bp6&utm_source=notes-share-action&utm_medium=web)**  How to architect an end-to-end blockchain ETL pipeline: source definition with SQD, four-stage PySpark transformation (clean → enrich → extract → materialize), DuckDB loading with idempotent upserts, and Airflow orchestration with a watermark-based DAG.

- **[Decoding Blockchain Data: Money Market Protocols](https://substack.com/@freemandaily/note/p-199692691?r=95bp6&utm_source=notes-share-action&utm_medium=web)**  A step-by-step walkthrough of how raw EVM event logs become structured lending data. Covers ABI anatomy, topic0 derivation, indexed vs non-indexed field decoding with `eth_abi`, Spark UDF design, and uint256 normalization. Using Aave V2 Borrow events as the worked example.

- **[Factory Contract Interaction](https://substack.com/@freemandaily/note/p-181307873?r=95bp6&utm_source=notes-share-action&utm_medium=web)**  Practical guide to interacting with the Uniswap V2 Factory Contract using Web3.py. Covers view vs write functions, pool creation, and how to decode the `PairCreated` event from a transaction receipt  including topic0 computation and data field slicing.

- **[Journey Into On-Chain Data Decoding and Automation](https://substack.com/@freemandaily/note/p-180308366?r=95bp6&utm_source=notes-share-action&utm_medium=web)**  An introduction to DeFi data analysis: why blockchain transparency is deeper than what explorers show, how AMMs and factory contracts work, and what makes on-chain data valuable for engineering and analytics.

→ **[Read all articles on Substack](https://substack.com/@freemandaily)**

---

## 📬 Get in Touch

- **Email:** Freemanonah@gmail.com
- **Twitter / X:** [@Freemandayly](https://x.com/freemandayly)
- **Telegram:** Freemanonah
- **LinkedIn:** [Onah Innocent](https://www.linkedin.com/in/onah-innocent-69ba32112/)
- **Substack:** [freemandaily.substack.com](https://substack.com/@freemandaily)
