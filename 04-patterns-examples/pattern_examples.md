# 📚 Data Quality Patterns – Examples

This document contains reusable, tool-agnostic **data quality patterns** with example implementations in popular tools.  
Each pattern maps to **Generic DQ Framework Phases** — mainly **Rule Definition & Validation**.

---

## 🧩 Pattern 1: Missing Values Check

**Goal:** Identify and flag rows with null or missing values in critical fields.

---

### 1. Generic Pattern
> Define a rule that checks for `NULL` or empty strings in specified columns and triggers a failure if thresholds are breached.

---

### 2. Implementation Examples

#### SQL (Generic)
```sql
SELECT *
FROM my_table
WHERE important_column IS NULL OR important_column = '';
```

#### Great Expectations
```python
from great_expectations.dataset import PandasDataset

df = PandasDataset(my_dataframe)
df.expect_column_values_to_not_be_null("important_column")
```

#### Deequ (Scala)
```scala
import com.amazon.deequ.VerificationSuite
import com.amazon.deequ.checks.Check

VerificationSuite()
  .onData(data)
  .addCheck(
    Check(CheckLevel.Error, "Data Quality Check")
      .isComplete("important_column")
  )
  .run()
```

#### Soda (YAML)
```yaml
checks for my_table:
  - missing_count(important_column) = 0
```

---

### 3. Variations
- Allow up to X% missing values
- Apply only for recent date partitions
- Combine with length/format checks

---

### 4. Use Cases
- Mandatory customer IDs
- Primary key integrity
- Required contact details

---

## 🧩 Pattern 2: Duplicate Records Check

**Goal:** Detect duplicate records based on one or more key columns.

---

### 1. Generic Pattern
> Group by the key columns and identify rows where the count > 1.

---

### 2. Implementation Examples

#### SQL (Generic)
```sql
SELECT key_column, COUNT(*) AS dup_count
FROM my_table
GROUP BY key_column
HAVING COUNT(*) > 1;
```

#### Great Expectations
```python
df.expect_column_values_to_be_unique("key_column")
```

#### Deequ (Scala)
```scala
check.isUnique("key_column")
```

#### Soda (YAML)
```yaml
checks for my_table:
  - duplicate_count(key_column) = 0
```

---

### 3. Variations
- Composite keys (multi-column)
- Partition-specific duplicates
- Ignore certain "soft" duplicates

---

### 4. Use Cases
- Ensuring primary key uniqueness
- Preventing double billing
- Removing redundant dimension entries

---

## 🧩 Pattern 3: Data Range Check

**Goal:** Validate that numeric or date values fall within acceptable boundaries.

---

### 1. Generic Pattern
> Define a min and max threshold for a field, and fail the check if values fall outside.

---

### 2. Implementation Examples

#### SQL (Generic)
```sql
SELECT *
FROM my_table
WHERE amount < 0 OR amount > 10000;
```

#### Great Expectations
```python
df.expect_column_values_to_be_between(
    "amount", min_value=0, max_value=10000
)
```

#### Deequ (Scala)
```scala
check.isNonNegative("amount")
check.hasMax("amount", _ <= 10000)
```

#### Soda (YAML)
```yaml
checks for my_table:
  - min(amount) >= 0
  - max(amount) <= 10000
```

---

### 3. Variations
- Date ranges (e.g., no future dates)
- Tolerance-based ranges
- Dynamic ranges based on historical data

---

### 4. Use Cases
- Financial transaction limits
- Valid age ranges
- Manufacturing measurement bounds

---

## 🧩 Pattern 4: Schema Validation

**Goal:** Ensure the dataset schema matches expected column names, types, and order.

---

### 1. Generic Pattern
> Compare the actual schema with a stored reference schema definition.

---

### 2. Implementation Examples

#### SQL (Generic)
Use system tables (e.g., `INFORMATION_SCHEMA`) to check column metadata.

```sql
SELECT column_name, data_type
FROM INFORMATION_SCHEMA.COLUMNS
WHERE table_name = 'my_table';
```

#### Great Expectations
```python
df.expect_table_columns_to_match_ordered_list(
    ["id", "name", "amount", "created_at"]
)
```

#### Deequ (Scala)
No direct schema check; use constraints on column existence & type.

```scala
check.hasColumn("id")
check.hasColumn("name")
```

#### Soda (YAML)
```yaml
checks for my_table:
  - schema:
      fail:
        when required column missing: [id, name, amount, created_at]
```

---

### 3. Variations
- Allow additional columns but enforce required ones
- Type checks only
- Column order flexibility

---

### 4. Use Cases
- ETL pipeline contract enforcement
- API data ingestion validation
- Data warehouse table governance
