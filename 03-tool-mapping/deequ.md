# Deequ – Data Quality Framework Mapping

Deequ is an open-source library from Amazon for **data quality validation at scale** using **Apache Spark**.

---

## Phase Coverage

| Generic DQ Phase | Coverage in Deequ | Notes |
|------------------|-------------------|-------|
| **1. Data Ingestion & Source Identification** | ✅ Any Spark-supported source | No native ingestion layer; depends on Spark DataFrame |
| **2. Profiling & Baseline Assessment** | ✅ Profiling API; constraint suggestion | Generates suggestions from data statistics |
| **3. Rule Definition & Configuration** | ✅ Scala or Python API (via PyDeequ) | DSL for defining constraints |
| **4. Validation & Execution** | ✅ Distributed execution in Spark | Suited for large-scale datasets |
| **5. Reporting & Alerting** | ⚠ JSON output only | Requires external systems for rich reports |
| **6. Remediation & Continuous Improvement** | ⚠ Limited; manual integration with ETL | Fits well into Spark-based DataOps pipelines |

---

## Strengths
- Scales to very large datasets
- Automated constraint suggestion
- Tight Spark integration

## Limitations
- No built-in dashboards
- Requires Scala/PySpark skills

