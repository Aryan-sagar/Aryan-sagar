# Aryan Sagar

### Building systems where **data, money, and decisions** meet.

I'm a graduate of **IIT Ropar** working toward Data Engineering, ML Engineering, and Systems roles.

I like building things from the ground up — not just models and dashboards, but the infrastructure underneath them: **data pipelines, financial ledgers, streaming systems, matching engines, distributed storage, and ML systems.**

My current obsession is simple:

> **How do you build software that remains correct when everything around it is trying to make it fail?**

---

## `01` — What I'm building

I'm developing a small **fintech systems portfolio** where each project explores a different class of production problem.

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

### 🏦 Transaction Data Warehouse & ELT Pipeline

**Problem:** Raw financial data is messy. Decisions shouldn't be.

Building an end-to-end warehouse that ingests transaction data, transforms it into analytical models, and exposes trustworthy datasets for downstream analysis.

`Python` `PostgreSQL` `dbt` `Airflow` `Docker`

---

### 💳 Idempotent Payments Ledger & Reconciliation Backend

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

---

### ⚡ Real-Time Risk & Fraud Scoring Engine

**Problem:** Fraud detection becomes much harder when decisions must happen while the transaction is happening.

Building a streaming architecture for:

```text
Transaction
    ↓
Event Stream
    ↓
Feature State
    ↓
Risk Model
    ↓
Risk Score
    ↓
Decision
```

Exploring online feature computation, streaming inference, model monitoring, and production ML concerns.

`Python` `Kafka` `Redis` `ML` `Docker`

---

### 📈 Limit Order Book Matching Engine & Backtester

**Problem:** Markets don't wait for your algorithm.

A low-level trading infrastructure project implementing:

* price-time priority
* order insertion
* cancellation
* matching
* market / limit orders
* trade generation
* order book state
* historical backtesting

The goal is to understand **market microstructure and performance from first principles**, rather than hiding behind a trading library.

`C++` `STL` `Algorithms` `Market Microstructure`

---

## `02` — Systems I'm exploring

### 🗄️ Distributed KV Store

A from-scratch **C++ distributed key-value store** exploring:

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

Learning by implementing the primitives myself:

**consensus → replication → persistence → recovery → distributed state**

`C++` `Raft` `Distributed Systems`

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

The interesting part wasn't calling `.fit()`.

It was designing a system capable of **searching through the space around the model**.

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
                  │
      Reliability ┼────── Performance
                  │
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
`Distributed Systems` · `Raft` · `Concurrency`

</td>
<td valign="top">

### 🧪 Engineering

`Pytest` · `System Design`  
`Algorithms` · `Performance Engineering`

</td>
</tr>
</table>

# Selected work

| Project                  | What it demonstrates                           |
| ------------------------ | ---------------------------------------------- |
| 🏦 Transaction Warehouse | Data Engineering · ELT · Analytics             |
| 💳 Payments Ledger       | Backend · Transactions · Financial Correctness |
| ⚡ Risk Engine            | Streaming · ML · Real-Time Systems             |
| 📈 Matching Engine       | C++ · Algorithms · Market Microstructure       |
| 🗄️ Distributed KV Store | Raft · Consensus · Distributed Systems         |
| 🧬 AutoML Framework      | ML · Optimization · Search                     |

---

# Beyond code

I also spend an unreasonable amount of time learning **filmmaking, photography, cinematography, and visual storytelling.**

Because good engineering and good filmmaking have something in common:

**the details matter.**

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
