# Aryan Sagar

### Building systems where **data, money, and decisions** meet.

I'm a graduate of **IIT Ropar** working toward Data Engineering, ML Engineering, and Systems roles.

I like building things from the ground up — not just models and dashboards, but the infrastructure underneath them: **data pipelines, financial ledgers, streaming systems, matching engines, distributed storage, and ML systems.**

My current obsession is simple:

> **How do you build software that remains correct when everything around it is trying to make it fail?**

---

## `01` — Fintech Systems Lab (complete)

A 4-project fintech systems portfolio where each project explores a different class of production problem. **All four are built and shipped.**

```text
                         FINTECH SYSTEMS LAB
                                │
             ┌──────────────────┼──────────────────┐
             │                  │                  │
             ▼                  ▼                  ▼
       DATA PLATFORM       MONEY MOVEMENT      DECISION SYSTEMS
             │                  │                  │
             ▼                  ▼                  ▼
       Data Warehouse       Payments Ledger    Risk / Fraud Engine
       + ELT Pipeline       + Reconciliation   + Streaming Inference
             │                                     │
             └──────────────────┬──────────────────┘
                                ▼
                       MARKET INFRASTRUCTURE
                                │
                                ▼
                  Limit Order Book + Backtester
```

### ✅ 🏦 Transaction Data Warehouse & ELT Pipeline

**Problem:** Raw financial data is messy. Decisions shouldn't be.

End-to-end warehouse that ingests transaction/account/merchant data, transforms it into a dimensional star-schema model (dim_accounts, dim_merchants, dim_date, fact_transactions), validates it with 48 automated dbt tests, and exposes it through an interactive analytics dashboard.

`Python` `PostgreSQL` `dbt` `Airflow` `Docker` `Streamlit`
**Repo:** [Transaction-Data-Warehouse-ELT-Pipeline](https://github.com/Aryan-sagar/Transaction-Data-Warehouse-ELT-Pipeline)

---

### ✅ 💳 Idempotent Payments Ledger & Reconciliation Backend

**Problem:** Money movement cannot depend on "probably".

A backend designed around financial correctness:

* double-entry ledger
* idempotent operations
* transaction state machines
* concurrency safety
* reconciliation
* immutable financial records
* failure recovery

`Python` `FastAPI` `PostgreSQL` `SQLAlchemy` `Pytest`
**Repo:** [Idempotent-Payments-Ledger-Reconciliation-Backend](https://github.com/Aryan-sagar/Idempotent-Payments-Ledger-Reconciliation-Backend)

---

### ✅ ⚡ Real-Time Risk & Fraud Scoring Engine

**Problem:** Fraud detection becomes much harder when decisions must happen while the transaction is happening.

```text
Transaction → Event Stream → Feature State → Risk Model → Risk Score → Decision
```

Explores online feature computation, streaming inference, model monitoring, and production ML concerns.

`Python` `Kafka` `Redis` `ML` `Docker`
**Repo:** [Real-Time-Risk-Fraud-Scoring-Engine](https://github.com/Aryan-sagar/-Real-Time-Risk-Fraud-Scoring-Engine)

---

### ✅ 📈 Limit Order Book Matching Engine & Backtester

**Problem:** Markets don't wait for your algorithm.

Price-time priority limit order book (heap + hashmap-of-deques per side, O(1) cancel via lazy deletion, ~185k orders/sec single-threaded), a FastAPI order-entry layer, a Poisson-arrival order-flow generator, tick persistence + controlled-speed replay, and a backtester (Sharpe ratio, max drawdown, win rate, slippage) with two reference strategies. 67 tests passing across the repo.

`Python` `FastAPI` `C++/Rust (hot path)` `Algorithms` `Market Microstructure`
**Repo:** [Limit-Order-Book-Matching-Engine-Backtester](https://github.com/Aryan-sagar/-Limit-Order-Book-Matching-Engine-Backtester)
**Remaining (optional stretch):** 3-node Raft-based state replication

---

## `02` — Currently building

Diversifying beyond fintech with new systems and ML projects.

### 🔄 Real-Time Collaborative Text Editor (in progress)

A Google-Docs-style collaborative editor built around a custom **RGA (Replicated Growable Array) CRDT implemented from scratch** — no off-the-shelf library like Yjs.

* Custom RGA sequence CRDT: deterministic concurrent-insert tie-breaking, tombstone deletes, out-of-order delivery buffer — validated with 2500+ randomized convergence trials plus an exhaustive permutation test
* FastAPI WebSocket relay server: per-client local replicas, materialized view for late-joiner snapshot sync, presence join/leave broadcasts — 13/13 integration tests passing

`Python` `FastAPI` `WebSockets` `CRDTs`
**Status:** M1 (CRDT core) and M2 (relay server) complete. Next: browser frontend, offline edit/reconnect merge, undo/redo.

### 🗄️ Distributed KV Store (planned)

A from-scratch **C++ distributed key-value store** exploring consensus, replication, and recovery, implementing the primitives directly rather than reaching for a library:

```text
Client
  │
  ▼
┌─────────┐      ┌─────────┐      ┌─────────┐
│ Node A  │◄────►│ Node B  │◄────►│ Node C  │
│ Leader  │      │Follower │      │Follower │
└─────────┘      └─────────┘      └─────────┘
       \             │             /
        └────────────┼────────────┘
                     ▼
                Raft Consensus
```

**consensus → replication → persistence → recovery → distributed state**

`C++` `Raft` `Distributed Systems`

### 🔎 Hybrid Semantic Search / Ranking Engine (planned)

A non-fintech ML project rounding out the new portfolio track — combining semantic retrieval with a learned ranking layer.

---

## `03` — ML experiments

Before focusing heavily on systems, I spent time building ML projects around real-world prediction problems.

### AutoML Framework

An experimental AutoML system combining:

* genetic algorithms
* automated feature engineering
* Optuna
* model selection
* hyperparameter optimization

The interesting part wasn't calling `.fit()`. It was designing a system capable of **searching through the space around the model**.

`Python` `Scikit-learn` `Optuna` `Genetic Algorithms`

---

## `04` — Currently learning

I'm deliberately moving deeper rather than collecting frameworks.

**Machine Learning**
* Transformers
* BERT
* Self-Supervised Learning
* Generative AI

**Systems**
* Distributed Systems
* Consensus Algorithms
* Storage Engines
* Concurrency
* Networking

**Engineering**
* System Design
* Performance Engineering
* Production ML
* Data Infrastructure

---

# Engineering philosophy

I care about the parts of software that are easy to ignore until production breaks them.

```text
             Correctness
                  ▲
                  │
      Reliability ┼────── Performance
                  │
                  ▼
             Observability
```

A model with great accuracy is interesting.

A model that survives **bad data, distribution shift, retries, concurrent requests, failures, and real traffic** is engineering.

---

## ⚙️ Engineering Stack

<table>
<tr>
<td valign="top" width="50%">

### 💻 Languages
`C` · `C++` · `Python` · `Java` · `SQL`

</td>
<td valign="top" width="50%">

### 🧠 Machine Learning
`PyTorch` · `TensorFlow` · `Scikit-learn`
`Pandas` · `NumPy` · `MLflow` · `Optuna`

</td>
</tr>
<tr>
<td valign="top">

### 🏗️ Data Engineering
`PostgreSQL` · `MySQL` · `dbt`
`Airflow` · `Kafka` · `Redis`

</td>
<td valign="top">

### ☁️ Infrastructure
`Docker` · `AWS` · `Git` · `GitHub`

</td>
</tr>
<tr>
<td valign="top">

### 🔌 Backend & Systems
`FastAPI` · `SQLAlchemy` · `REST APIs`
`WebSockets` · `CRDTs` · `Distributed Systems` · `Raft` · `Concurrency`

</td>
<td valign="top">

### 🧪 Engineering
`Pytest` · `System Design`
`Algorithms` · `Performance Engineering`

</td>
</tr>
</table>

# Selected work

| Project | Status | What it demonstrates |
| --- | --- | --- |
| 🏦 Transaction Warehouse | ✅ Built | Data Engineering · ELT · Analytics |
| 💳 Payments Ledger | ✅ Built | Backend · Transactions · Financial Correctness |
| ⚡ Risk Engine | ✅ Built | Streaming · ML · Real-Time Systems |
| 📈 Matching Engine & Backtester | ✅ Built | Algorithms · Market Microstructure · Backtesting |
| 🔄 Collaborative Text Editor | 🔄 In progress | CRDTs · WebSockets · Distributed State |
| 🗄️ Distributed KV Store | 🗓️ Planned | Raft · Consensus · Distributed Systems |
| 🧬 AutoML Framework | ✅ Built | ML · Optimization · Search |

---

# Beyond code

I also spend an unreasonable amount of time learning **filmmaking, photography, cinematography, and visual storytelling.**

Because good engineering and good filmmaking have something in common: **the details matter.**

---

## 📊 GitHub

<p align="center">
  <img
    src="https://github-readme-stats.vercel.app/api?username=Aryan-sagar&show_icons=true&hide_border=true&theme=transparent&rank_icon=github&include_all_commits=true"
    height="170"
  />
  <img
    src="https://github-readme-stats.vercel.app/api/top-langs/?username=Aryan-sagar&layout=compact&hide_border=true&theme=transparent"
    height="170"
  />
</p>

<p align="center">
  <img
    src="https://streak-stats.demolab.com?user=Aryan-sagar&theme=transparent&hide_border=true"
    height="170"
  />
</p>

---

# Let's connect

**LinkedIn**
[www.linkedin.com/in/aryan-sagar-755947254](http://www.linkedin.com/in/aryan-sagar-755947254)

**Email**
[aryansagar.workspace@gmail.com](mailto:aryansagar.workspace@gmail.com)

**GitHub**
github.com/Aryan-sagar

---

<p align="center">
  <sub>Building. Breaking. Measuring. Rebuilding.</sub>
</p>
