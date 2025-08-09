# 📊 Data Testing Frameworks

A curated knowledge repository for **Data Quality (DQ)** and **Automated Data Testing** practices — from fundamentals, framework types, and tool mappings to reusable test patterns.

---

## 📂 Repository Structure

```
.
├── 01-basics/                  # Core concepts & foundational knowledge
│   ├── automation_vs_data_testing.md       # Difference between automation testing & data testing
│   └── generic_data_quality_framework.md   # The Generic Data Quality (DQ) Framework with diagram
│
├── 02-framework-types/         # Types & evolution of testing frameworks
│   ├── automation_framework_types.md       # Types of automation testing frameworks
│   └── evolution_of_frameworks.md          # Evolution of frameworks in automation & data testing
│
├── 03-tool-mapping/            # Mapping DQ tools to framework phases
│   ├── deequ.md
│   ├── dqx.md
│   ├── generic_tool_mapping.md
│   ├── great_expectations.md
│   ├── soda.md
│   ├── tool-comparison.md                  # Tabular comparison of tools
│   └── README.md                           # Tool mapping index
│
├── 04-patterns-examples/       # Reusable data testing patterns
│   └── pattern_examples.md                  # Generic + tool-specific examples for common checks
│
├── diagrams/                   # PNGs & diagrams used across documents
│
├── LICENSE                     # License for repository usage
├── README.md                   # This file
└── references.md               # Reference links, papers, and documentation
```

---

## 🚀 Purpose

This repository serves as a **knowledge base** and **quick-start guide** for:
- Understanding the difference between automation testing & data testing.
- Learning the **Generic Data Quality Framework** that applies across tools.
- Exploring evolution from classic automation testing to data testing frameworks.
- Mapping popular data testing tools to framework phases.
- Using **ready-made patterns** for common data quality checks.

---

## 🧩 Key Topics Covered

### 1️⃣ Basics
- **Automation vs. Data Testing** — how data testing differs in scope & focus.
- **Generic DQ Framework** — ingestion → profiling → rule definition → validation → reporting → remediation.

### 2️⃣ Framework Types & Evolution
- Automation framework types: Modular, Data-driven, Keyword-driven, Hybrid, BDD, TDD.
- Evolution from Selenium/Cucumber to modern data testing tools.

### 3️⃣ Tool Mapping
- Detailed breakdown for **Great Expectations, Deequ, Soda, DQX**.
- **Tool comparison matrix** for quick decision-making.

### 4️⃣ Patterns & Examples
- Missing values check
- Duplicate detection
- Data range validation
- Schema validation
- Tool-agnostic + specific examples in SQL, Python, YAML, Scala.

---

## 📌 How to Use This Repo
1. Start with `01-basics/` to understand the fundamentals.
2. Explore `02-framework-types/` for historical & conceptual evolution.
3. Use `03-tool-mapping/` to compare tools & see where they fit in the DQ framework.
4. Apply `04-patterns-examples/` in your own pipelines for quick wins.
5. Reference diagrams in `/diagrams` when documenting or presenting.

---

## 📜 License
This project is licensed under the terms of the [MIT License](LICENSE).

---

## 🤝 Contributing
Feel free to submit issues, improvements, or additional tool mappings/patterns via pull requests.

---
