# Generic Mapping: Data Quality Framework → Tool Capabilities

This file provides a **neutral, vendor-agnostic** mapping between the **Generic Data Quality Framework** and common categories of tool features.

---

## Framework Phases and Feature Mapping

1. **Data Ingestion & Source Identification**
   - Data connectors (JDBC, REST APIs, file systems, cloud storage)
   - Metadata extraction
   - Schema auto-discovery

2. **Profiling & Baseline Assessment**
   - Column statistics (min, max, avg, std dev)
   - Null/duplicate detection
   - Pattern frequency analysis

3. **Rule Definition & Configuration**
   - Declarative syntax (YAML, JSON)
   - Programmatic APIs (Python, Scala, SQL)
   - Built-in and custom rules

4. **Validation & Execution**
   - Batch mode (ETL checkpoints, scheduled jobs)
   - Streaming mode (real-time data quality checks)
   - Scalable engines (Spark, Flink)

5. **Reporting & Alerting**
   - CLI summaries
   - HTML/PDF/JSON reports
   - Alerts via Slack, email, Jira, PagerDuty

6. **Remediation & Continuous Improvement**
   - Auto-trigger remediation scripts
   - Data quality dashboards for trend monitoring
   - Rule evolution & version control

---

## Notes
- This mapping allows you to **plug in any tool** by matching its features to the framework.
- A single tool may **cover multiple phases**, but rarely all.
- Multi-tool setups are common in large data environments.

