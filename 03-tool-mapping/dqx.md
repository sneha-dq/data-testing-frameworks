# DQX – Data Quality Framework Mapping

DQX is a **customizable, lightweight framework** for **data quality monitoring** with flexible rule definitions.

---

## Phase Coverage

| Generic DQ Phase | Coverage in DQX | Notes |
|------------------|-----------------|-------|
| **1. Data Ingestion & Source Identification** | ✅ Connectors for files, APIs, databases | Extensible ingestion layer |
| **2. Profiling & Baseline Assessment** | ✅ Supports custom profiling scripts | No automated profiling unless implemented |
| **3. Rule Definition & Configuration** | ✅ Config-driven rules | YAML/JSON-based, easily extended |
| **4. Validation & Execution** | ✅ Batch processing; streaming possible | Can integrate with orchestration tools |
| **5. Reporting & Alerting** | ✅ Basic reporting; extendable via APIs | Can integrate with BI tools |
| **6. Remediation & Continuous Improvement** | ✅ Hooks for auto-remediation scripts | Custom logic needed |

---

## Strengths
- Highly customizable
- Flexible integrations
- Simple learning curve

## Limitations
- Depends heavily on user implementation
- Small community

