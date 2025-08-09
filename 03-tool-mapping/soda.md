# Soda – Data Quality Framework Mapping

Soda provides **data monitoring and testing** via SQL-based checks, with strong **alerting and integration capabilities**.

---

## Phase Coverage

| Generic DQ Phase | Coverage in Soda | Notes |
|------------------|------------------|-------|
| **1. Data Ingestion & Source Identification** | ✅ Supports multiple SQL data sources | No ETL; connects directly to databases/data warehouses |
| **2. Profiling & Baseline Assessment** | ✅ Profiling commands & metric collection | Can auto-discover schema and anomalies |
| **3. Rule Definition & Configuration** | ✅ YAML-based checks; SQL expressions | Very declarative; low-code |
| **4. Validation & Execution** | ✅ Runs checks in CI/CD or scheduled jobs | Good for both batch and incremental checks |
| **5. Reporting & Alerting** | ✅ Built-in Slack, MS Teams, Jira integration | Strong operational alerting |
| **6. Remediation & Continuous Improvement** | ⚠ Relies on external systems for fixes | Focused on detection rather than correction |

---

## Strengths
- Excellent integration with cloud warehouses
- Low-code check definitions
- Strong alerting

## Limitations
- SQL-centric (non-SQL data needs transformation)
- Not a big library of built-in complex rules

