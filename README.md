<div align="center">

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:070a09,100:0c1210&height=160&section=header&text=ARYAN%20SAGAR&fontSize=42&fontColor=5eead4&fontAlignY=42&desc=Systems%20Engineer%20%2F%2F%20ML%20Engineer%20%2F%2F%20Data%20Builder&descAlignY=62&descSize=16&descColor=7fa89c&animation=fadeIn)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=18&pause=1200&color=FFB454&center=true&vCenter=true&width=600&lines=I+build+systems+where+data%2C+money%2C+and+decisions+meet.;Not+demos.+Not+.fit()+and+call+it+a+day.;Systems+that+stay+correct+when+everything+breaks.)](https://git.io/typing-svg)

<a href="https://www.iitrpr.ac.in/"><img src="https://img.shields.io/badge/IIT%20Ropar-Graduate-8B0000?style=for-the-badge&logo=academia&logoColor=white" alt="IIT Ropar"></a>
<a href="https://github.com/Aryan-sagar"><img src="https://img.shields.io/badge/Focus-Systems-1f2937?style=for-the-badge&logo=github&logoColor=white" alt="Systems"></a>
<a href="https://github.com/Aryan-sagar"><img src="https://img.shields.io/badge/Focus-Machine%20Learning-2563eb?style=for-the-badge&logo=python&logoColor=white" alt="ML"></a>
<a href="https://github.com/Aryan-sagar"><img src="https://img.shields.io/badge/Focus-Data%20Engineering-059669?style=for-the-badge&logo=apache&logoColor=white" alt="Data"></a>

</div>

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

*(click a boss to expand )*

<details>
<summary><b>🏦 BOSS: CHAOTIC FINANCIAL DATA</b> — raw data is messy, decisions shouldn't be</summary>

<br>

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

</details>

<details>
<summary><b>💳 BOSS: MONEY + RETRIES + CONCURRENCY</b> — money movement cannot depend on "probably"</summary>

<br>

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

</details>

<details>
<summary><b>⚡ BOSS: DECIDE BEFORE THE FRAUDSTER DOES</b> — a streaming ML system that doesn't wait for tomorrow's batch job</summary>

<br>

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
                     watermarking                            └── BLOCK
                     exactly-once
```

**Explores:** streaming inference · online feature computation · feature state · event-time processing · watermarks · model serving · risk decisions · production ML failure modes

`Python` `Flink` `Kafka` `Redis` `Docker`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/-Real-Time-Risk-Fraud-Scoring-Engine)**

</details>

<details>
<summary><b>📈 BOSS: THE MARKET</b> — markets don't wait for your algorithm</summary>

<br>

A from-scratch market microstructure system implementing a price-time-priority order book and research backtesting infrastructure.

**Current implementation:** price-time priority · heap-based price levels · hashmap-of-deques · lazy deletion · O(1) cancel path · FastAPI order-entry layer · Poisson order-flow generator · tick persistence · controlled-speed replay · backtesting engine · reference strategies · Sharpe ratio · max drawdown · win rate · slippage analysis · **67 tests passing**

**Performance:** `~185,000 orders/sec` (single-threaded)

`Python` `FastAPI` `C++ / Rust hot-path exploration` `Algorithms` `Market Microstructure`

**[→ ENTER THE REPOSITORY](https://github.com/Aryan-sagar/-Limit-Order-Book-Matching-Engine-Backtester)**

</details>

<details>
<summary><b>🌊 BOSS: THE MINI LAKE</b> — storage is a system, not a folder</summary>

<br>

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

</details>

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

<details>
<summary><b>🧬 AutoML Framework</b> — exploring the search space around the model</summary>

<br>

```text
DATA → FEATURE ENGINEERING → [ GENETIC SEARCH + OPTUNA HPO ] → MODEL SEARCH → WINNER
```

`Scikit-learn` `Optuna` `Genetic Algorithms` `Python`

</details>

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
├── Scikit-learn               █████████░
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

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Aryan-sagar&theme=react-dark&hide_border=true&bg_color=070a09&color=5eead4&line=5eead4&point=ffb454" alt="Activity graph"/>
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

<div align="center">

### Want to talk systems, ML, data, markets, or just build something ridiculous?

**[LinkedIn](http://www.linkedin.com/in/aryan-sagar-755947254)** · **[GitHub](https://github.com/Aryan-sagar)** · **[Email](mailto:aryansagar.workspace@gmail.com)**

</div>

---

<div align="center">

```text
BUILD → BREAK → MEASURE → UNDERSTAND → REBUILD

                         ↓

              MAKE IT SURVIVE REALITY.
```

### `SYSTEM STATUS: BUILDING`

</div>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:0c1210,100:070a09&height=100&section=footer)
