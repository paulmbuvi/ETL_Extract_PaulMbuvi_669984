# ETL Extract & Load Lab

**Name:** Paul Mbuvi  
**Student ID:** 669984  

---

## 🔍 Description
This project demonstrates Full and Incremental **Extraction** and **Loading** techniques using a synthetic sales dataset. The notebooks walk through the ETL process, including loading the transformed data into structured formats like **Parquet** and **SQLite**.

---

## 🛠️ Tools Used
- Python
- pandas
- SQLite (`sqlite3`)
- fastparquet
- Jupyter Notebook

---

## 🚀 How to Run

### 1. Extraction
- Open `etl_extract.ipynb`
- Run all cells to simulate full and incremental extraction

### 2. Load
- Open `etl_load.ipynb`
- Run all cells to:
  - Load transformed CSVs
  - Save data to Parquet files
  - Save data to SQLite databases
  - Preview loaded data

---

## 📁 Files

| File/Folder                 | Description                                  |
|----------------------------|----------------------------------------------|
| `etl_extract.ipynb`        | Extraction logic                             |
| `etl_load.ipynb`           | Load logic (Parquet + SQLite)                |
| `transformed/`             | Cleaned datasets (`transformed_full.csv`, `transformed_incremental.csv`) |
| `loaded_data/`             | Output folder with `.parquet` and `.db` files |
| `last_extraction.txt`      | Timestamp log for incremental extraction     |
| `.gitignore`               | Files excluded from Git tracking             |

---

## 🧾 Lab 5 – Load Summary

- Loaded full and incremental transformed data
- Saved to **Parquet** using `pandas.to_parquet()`
- Saved to **SQLite** using `sqlite3` and `to_sql()`
- Verified with `.head()` and SQL SELECT queries

**Output Location:** `loaded_data/`

**Sample Code:**
```python
full_df.to_parquet("loaded_data/full_data.parquet", index=False)

with sqlite3.connect("loaded_data/full_data.db") as conn:
    full_df.to_sql("full_data", conn, if_exists="replace", index=False)
