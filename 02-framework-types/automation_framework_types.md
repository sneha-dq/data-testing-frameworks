# Types of Automation Testing Frameworks and Data Testing Equivalents

This document maps common **software automation testing frameworks** to their **data testing counterparts**.

| Framework Type             | Description in Software Testing                               | Corresponding Pattern in Data Testing                                    | Example Tools (Data) |
|----------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------|----------------------|
| **Linear / Scripted**      | Sequential test steps hardcoded in scripts                    | SQL/Python scripts with fixed validation queries                          | Custom SQL, PyODBC   |
| **Modular**                | Tests split into reusable modules                             | Reusable data quality check functions or classes                          | Python DQ modules    |
| **Data-Driven**            | Test logic fixed, data inputs externalized                    | Rule logic fixed, thresholds and rules in config files                    | GE YAML, Soda checks |
| **Keyword-Driven**         | Actions represented as keywords                               | Quality dimensions or rule types as keywords                              | Excel keyword DQ     |
| **Hybrid**                 | Mix of data-driven and keyword-driven                         | Parameterized + business-readable data checks                             | GE + custom configs  |
| **BDD (Behavior-Driven)**  | Scenarios in Gherkin mapped to code                           | Business-readable DQ rules (“Given dataset X, expect no nulls in Y”)      | GE natural language  |
| **TDD (Test-Driven)**      | Write tests before implementing code                          | Write DQ rules/contracts before building ETL                              | dbt tests first      |
| **Continuous Testing**     | Integrated with CI/CD for ongoing checks                      | Integrated with DataOps pipelines (Airflow, Jenkins, dbt Cloud)           | Soda in CI/CD        |

## Observation
The **patterns** are largely similar; the difference is in **what** is tested and the **tooling** used.

