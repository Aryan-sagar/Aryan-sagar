# ⚡ ARYAN SAGAR

### `SYSTEMS ENGINEER // ML ENGINEER // DATA BUILDER`

> **I build systems where data, money, and decisions meet.**
>
> Not demos. Not `.fit()` and call it a day.
> **Systems that remain correct when everything around them goes wrong.**

<p align="center">
  <a href="https://www.iitrpr.ac.in/">
    <img src="https://img.shields.io/badge/IIT%20Ropar-Graduate-8B0000?style=for-the-badge&logo=academia&logoColor=white" alt="IIT Ropar">
  </a>
  <a href="https://github.com/Aryan-sagar">
    <img src="https://img.shields.io/badge/Focus-Systems-1f2937?style=for-the-badge&logo=github&logoColor=white" alt="Systems">
  </a>
  <a href="https://github.com/Aryan-sagar">
    <img src="https://img.shields.io/badge/Focus-Machine%20Learning-2563eb?style=for-the-badge&logo=python&logoColor=white" alt="ML">
  </a>
  <a href="https://github.com/Aryan-sagar">
    <img src="https://img.shields.io/badge/Focus-Data%20Engineering-059669?style=for-the-badge&logo=apache&logoColor=white" alt="Data">
  </a>
</p>

---

## `> BOOT_SEQUENCE`

```text
INITIALIZING ARYAN.SAGAR...

[████████████████████████████████] 100%

IDENTITY        → SYSTEMS / ML / DATA
ENVIRONMENT     → DISTRIBUTED SYSTEMS / STREAMING
PRIMARY WEAPON  → PYTHON / C++ / SQL / FLINK
CURRENT MODE    → BUILD
STATUS          → ONLINE

MISSION:
    Build software that stays correct
    when reality stops cooperating.

    • retries & race conditions
    • duplicate requests & bad data
    • network failures & concurrent writes
    • distribution shift & partial outages
    • exactly-once semantics & backpressure
    • out-of-order events & late data

SYSTEM READY.
```

---

## `01` — THE MAP

```text
                         ┌─────────────────────────┐
                         │     ARYAN'S LAB         │
                         │   (a working system)    │
                         └────────────┬────────────┘
                                      │
        ┌──────────────┬──────────────┼──────────────┬──────────────┐
        │              │              │              │              │
        ▼              ▼              ▼              ▼              ▼
   DATA LAKE      STREAMING       MONEY         DECISION        MARKET
   (storage)      (compute)      (ledger)       (real-time)     (microstructure)
        │              │              │              │              │
        ▼              ▼              ▼              ▼              ▼
   Transaction    Flink Jobs      Payments      Risk Scoring    Limit Order
   DW + ELT       + Kafka         Ledger        Engine          Book Engine
   Pipeline       + Redis         + Recon.      + Streaming     + Backtester
        │              │              │              │              │
        └──────────────┴──────────────┼──────────────┴──────────────┘
                                      │
                                      ▼
                         DATA → DECISIONS → MONEY
```

---

## `02` — BOSS FIGHTS DEFEATED

> [!WARNING]
> ### 🏦 BOSS: CHAOTIC FINANCIAL DATA
> **Raw data is messy. Decisions shouldn't be.**

An end-to-end financial data platform — raw transactions, accounts, and merchants flowing into an analytics-ready dimensional warehouse, with a mini data lake as the landing zone.

```text
SOURCE SYSTEMS
      │
      ▼
┌─────────────────┐
│  MINI DATA LAKE │  ← raw immutable landing zone
│  (Parquet files)│     partitioned by date / source
└────────┬────────┘
         │
         ▼
   ┌──────────┐
   │ AIRFLOW  │  ← orchestration + retries + backfills
   └────┬─────┘
        │
        ▼
   ┌──────────┐
   │ POSTGRES │  ← warehouse
   └────┬─────┘
        │
        ▼
   ┌──────────┐
   │   DBT    │  ← dim_accounts · dim_merchants · dim_date · fact_transactions
   └────┬─────┘
        │
        ▼
   48 TESTS → ANALYTICS → STREAMLIT
```

**What I cared about:** dimensional modeling · ELT architecture · data quality · orchestration · reproducibility · automated validation · **lake + warehouse split**

`Python` `PostgreSQL` `dbt` `Airflow` `Docker` `Streamlit` `Parquet`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/Transaction-Data-Warehouse-ELT-Pipeline)**

---

> [!DANGER]
> ### 💳 BOSS: MONEY + RETRIES + CONCURRENCY
> **Money movement cannot depend on "probably".**

A backend designed around financial correctness rather than simply returning `200 OK`.

```text
CLIENT → API REQUEST → IDEMPOTENCY CHECK → TRANSACTION STATE → DOUBLE-ENTRY LEDGER
                                                                     ├── ACCOUNT A
                                                                     └── ACCOUNT B
                                                                     ↓
                                                            RECONCILIATION → FAILURE RECOVERY
```

**Built around:** `✓` Double-entry accounting · `✓` Idempotent operations · `✓` Transaction state machines · `✓` Concurrency safeguards · `✓` Immutable financial records · `✓` Reconciliation · `✓` Failure recovery

`Python` `FastAPI` `PostgreSQL` `SQLAlchemy` `Pytest`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/Idempotent-Payments-Ledger-Reconciliation-Backend)**

---

> [!IMPORTANT]
> ### ⚡ BOSS: DECIDE BEFORE THE FRAUDSTER DOES
> **A streaming ML system where the model doesn't get the luxury of waiting for tomorrow's batch job.**

```text
TRANSACTION EVENTS
        │
        ▼
   ┌──────────┐        ┌──────────┐        ┌──────────┐        ┌──────────┐
   │  KAFKA   │───────▶│  FLINK   │───────▶│  REDIS   │───────▶│  MODEL   │
   │  topic   │        │  jobs    │        │  state   │        │  serve   │
   └──────────┘        └────┬─────┘        └──────────┘        └────┬─────┘
                            │                                       │
                            ▼                                       ▼
                     windowed aggs                          risk score
                     event-time                             ├── ALLOW
                     watermarking                           └── BLOCK
                     exactly-once
```

**Explores:** streaming inference · online feature computation · feature state · event-time processing · watermarks · model serving · risk decisions · production ML failure modes

`Python` `Flink` `Kafka` `Redis` `Docker`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/-Real-Time-Risk-Fraud-Scoring-Engine)**

---

> [!NOTE]
> ### 📈 BOSS: THE MARKET
> **Markets don't wait for your algorithm.**

A from-scratch market microstructure system implementing a price-time-priority order book and research backtesting infrastructure.

**Current implementation:** price-time priority · heap-based price levels · hashmap-of-deques · lazy deletion · O(1) cancel path · FastAPI order-entry layer · Poisson order-flow generator · tick persistence · controlled-speed replay · backtesting engine · reference strategies · Sharpe ratio · max drawdown · win rate · slippage analysis · **67 tests passing**

**Performance:** `~185,000 orders/sec` (single-threaded)

`Python` `FastAPI` `C++ / Rust hot-path exploration` `Algorithms` `Market Microstructure`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/-Limit-Order-Book-Matching-Engine-Backtester)**

---

> [!TIP]
> ### 🌊 BOSS: THE MINI LAKE
> **Storage is a system, not a folder.**

A small lakehouse built to understand the storage layer underneath everything else — not to hide it behind a managed service.

```text
STREAMS / BATCH SOURCES
          │
          ▼
   ┌─────────────┐
   │  INGESTION  │  ← schema-on-write, not schema-on-read panic
   └──────┬──────┘
          │
          ▼
   ┌─────────────┐
   │  RAW LAYER  │  ← append-only · immutable · partitioned
   │  (Parquet)  │     by date / source / hour
   └──────┬──────┘
          │
          ▼
   ┌─────────────┐
   │  CURATED    │  ← cleaned · deduped · typed
   └──────┬──────┘
          │
          ▼
   ┌─────────────┐
   │  SERVING    │  ← queryable · compacted · small files merged
   └─────────────┘
```

**Exploring:** file formats (Parquet / ORC) · partitioning strategy · compaction · small-file problem · schema evolution · metadata catalogs · **when a lake beats a warehouse (and when it doesn't)**

`Python` `Parquet` `S3 / MinIO` `DuckDB` `Polars`

**[→ WATCH THE BUILD](https://github.com/Aryan-sagar)**

---

## `03` — CURRENT MISSION

### 🔄 REAL-TIME COLLABORATIVE TEXT EDITOR
`STATUS: [██████████████████░░] 80%`

Building a Google-Docs-style collaborative editor **without hiding the hard part behind Yjs or another CRDT library.** The core distributed state mechanism is built from scratch.

```text
USER A → LOCAL RGA → WEBSOCKET → FASTAPI RELAY → USER B (LOCAL RGA)
                                                → USER C (LOCAL RGA)
                                                ↓
                                          CONVERGENCE
```

**Already defeated:**
`✓` Custom RGA sequence CRDT · `✓` Deterministic concurrent insertion · `✓` Tombstone deletion · `✓` Out-of-order delivery buffering · `✓` 2,500+ randomized convergence trials · `✓` Exhaustive permutation testing · `✓` Materialized late-joiner snapshots · `✓` Presence broadcasts · `✓` WebSocket relay · `✓` 13/13 integration tests

**Next boss:**
`[ ]` Browser frontend · `[ ]` Offline editing · `[ ]` Reconnect + merge · `[ ]` Undo / redo

`Python` `FastAPI` `WebSockets` `CRDTs` `Distributed State`

**[→ WATCH THE BUILD](https://github.com/Aryan-sagar)**

---

## `04` — SIDE QUESTS

Not everything I build belongs to the main lab.

### 🧬 AutoML Framework
An experimental AutoML system exploring the search space **around** the model.

```text
DATA → FEATURE ENGINEERING → [ GENETIC SEARCH + OPTUNA HPO ] → MODEL SEARCH → WINNER
```

`Scikit-learn` `Optuna` `Genetic Algorithms` `Python`

---

## `05` — SKILL TREE

```text
SYSTEMS
├── Distributed Systems       █████████░
├── Concurrency               ████████░░
├── Networking                ███████░░░
├── Storage                   ███████░░░
├── Consensus / Raft          ██████░░░░
└── Performance Engineering   ████████░░

DATA
├── PostgreSQL                █████████░
├── SQL                       █████████░
├── dbt                       ████████░░
├── Airflow                   ████████░░
├── Kafka                     ████████░░
├── Redis                     ████████░░
├── Flink                     ███████░░░
├── Parquet / Lake            ███████░░░
└── DuckDB / Polars           ██████░░░░

ML
├── PyTorch                   ████████░░
├── TensorFlow                ███████░░░
├── Scikit-learn              █████████░
├── ML Systems                ███████░░░
├── Transformers              ██████░░░░
└── Production ML             ███████░░░

ENGINEERING
├── Python                    █████████░
├── C++                       ████████░░
├── Java                      ███████░░░
├── FastAPI                   █████████░
├── Docker                    ████████░░
└── Testing                   █████████░
```

*Bars represent current working depth, not a claim of mastery.*

---

## `06` — TECH ARSENAL

- **Languages:** `C` `C++` `Python` `Java` `SQL`
- **Data:** `PostgreSQL` `MySQL` `dbt` `Airflow` `Kafka` `Flink` `Redis` `Parquet` `DuckDB` `Polars`
- **ML:** `PyTorch` `TensorFlow` `Scikit-learn` `Pandas` `NumPy` `MLflow` `Optuna`
- **Backend:** `FastAPI` `SQLAlchemy` `REST` `WebSockets`
- **Infrastructure:** `Docker` `AWS` `MinIO` `Git` `GitHub`
- **Systems:** `CRDTs` `Distributed Systems` `Raft` `Concurrency` `Algorithms` `Performance Engineering` `Stream Processing`

---

## `07` — THE RULES

I optimize for a few things.

```text
┌────────────────────────────────────────────┐
│                                            │
│                CORRECTNESS                 │
│                     ▲                      │
│                     │                      │
│         RELIABILITY ┼ PERFORMANCE          │
│                     │                      │
│                     ▼                      │
│               OBSERVABILITY                │
│                                            │
└────────────────────────────────────────────┘
```

1. **Correctness before cleverness:** A system that produces the wrong answer faster is still wrong.
2. **Failure is a feature:** Retries, duplicate messages, race conditions, partial failures, and corrupted assumptions aren't edge cases. They're the system.
3. **Measure it:** If performance matters: **benchmark it.** If reliability matters: **test it.** If a model matters: **evaluate it.**
4. **Understand the abstraction:** I like frameworks. I like them much less when I don't understand what they're hiding.

---

## `08` — CURRENTLY LEARNING

```text
                ┌─────────────────┐
                │   GO DEEPER     │
                └────────┬────────┘
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
   DISTRIBUTED       ML SYSTEMS       STORAGE
    SYSTEMS
        │                │                │
   • Consensus      • Transformers   • WAL / LSM
   • Replication    • Serving        • Compaction
   • Fault Tol.     • Evaluation     • Indexing
   • Failure Rec.   • Monitoring     • Recovery
   • Exactly-once   • Feature store  • Lakehouse
```

---

## `09` — THE NUMBERS

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Aryan-sagar&show_icons=true&hide_border=true&theme=radical&include_all_commits=true" height="170" alt="Stats"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Aryan-sagar&layout=compact&hide_border=true&theme=radical" height="170" alt="Top Langs"/>
  <img src="https://streak-stats.demolab.com?user=Aryan-sagar&theme=radical&hide_border=true" height="170" alt="Streak"/>
</p>

---

## `10` — ACHIEVEMENT LOG

```text
╔══════════════════════════════════════════════════════╗
║                  ACHIEVEMENTS                        ║
╠══════════════════════════════════════════════════════╣
║                                                      ║
║  🏦 DATA ARCHITECT                                   ║
║  Built an end-to-end financial warehouse             ║
║                                                      ║
║  💳 LEDGER KEEPER                                    ║
║  Built an idempotent double-entry payment system     ║
║                                                      ║
║  ⚡ REAL-TIME HUNTER                                 ║
║  Built a streaming fraud decision engine             ║
║                                                      ║
║  📈 MARKET MAKER                                     ║
║  Built a limit-order matching engine                 ║
║                                                      ║
║  🧠 DISTRIBUTED THINKER                              ║
║  Built an RGA CRDT from scratch                      ║
║                                                      ║
║  🌊 LAKE DIVER                                       ║
║  Built a mini lakehouse + Flink streaming layer      ║
║                                                      ║
║  🧪 EXPERIMENTALIST                                  ║
║  Built an AutoML search framework                    ║
║                                                      ║
╚══════════════════════════════════════════════════════╝
```

---

## `11` — OUTSIDE THE TERMINAL

When I'm not thinking about distributed state, race conditions, or financial ledgers:

🎬 Filmmaking · 📷 Photography · 🎞️ Cinematography · 🎸 Guitar · 📚 Psychology, philosophy & history

> *Because engineering and filmmaking share one annoying truth:*
> **The details matter.**

---

## `12` — CONNECT

<p align="center">

### Want to talk systems, ML, data, markets, or just build something ridiculous?

**[LinkedIn](http://www.linkedin.com/in/aryan-sagar-755947254)** · **[GitHub](https://github.com/Aryan-sagar)** · **[Email](mailto:aryansagar.workspace@gmail.com)**

</p>

---

<p align="center">

```text
BUILD → BREAK → MEASURE → UNDERSTAND → REBUILD

                         ↓

              MAKE IT SURVIVE REALITY.
```

### `SYSTEM STATUS: BUILDING`

</p>
