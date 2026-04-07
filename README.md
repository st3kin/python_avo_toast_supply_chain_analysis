# 🥑 Avocado Toast Supply Chain Analysis 🥑

> **Goal:** Trace the global supply chains behind the simple yet iconic avocado toast using real-world food origin data.

---

## Project Overview

You're in Sydney, crafting a plate of avocado toast; a staple of modern breakfast culture. But have you ever wondered where those ingredients come from? In this project, I explore the international supply chain of this five-ingredient dish:

- **Avocado**
- **Lemon**
- **Salt flakes**
- **Sourdough bread**
- **Extra virgin olive oil**

Using the Open Food Facts database, I conducted an origin analysis of three primary ingredients: avocados, olive oil, and sourdough bread. The goal was to highlight the global complexity behind a seemingly simple meal.

---

## Data Sources

Each ingredient is supported by two files located in the `CSV_files/` directory:

- **CSV files** (`avocado.csv`, `olive_oil.csv`, `sourdough.csv`) contain product-level metadata and origin tags.
- **TXT files** list the relevant category tags for filtering out non-matching entries.

I focused on:
- Filtering by relevant `categories_tags`.
- Cleaning inconsistent or multilingual `origins` data.
- Aggregating the top origin countries per ingredient.

---

## Data Cleaning

Each dataset required country name standardisation due to inconsistent labeling (e.g., `"Espagne"` → `"Spain"`, `"Pérou"` → `"Peru"`). I used dictionaries to normalise values and converted `origins` to categorical dtype for memory efficiency.

---

## Methodology

```python
def read_and_filter_data(df, colname, top_n=1):
    # Reads through the file, counts the countries of origin, and returns the top n rows
```

Each product file was processed to:
- Select only relevant columns (e.g., `product_name_en`, `origins`, `categories_tags`).
- Normalise country names.
- Count frequency of each country listed in the `origins` field.
- Display the top contributor(s) per ingredient.

---

## Findings

| Ingredient     | Top Origin(s)       |
|----------------|---------------------|
| Avocado        | Peru                |
| Olive Oil      | Spain       |
| Sourdough Bread| United Kingdom      |

Even the simplest meal is the product of a vast, interconnected global food system.

---

## Tools Used

| Purpose              | Tool            |
|----------------------|-----------------|
| Data Analysis        | Python, Pandas  |
| Data Source          | Open Food Facts |
| File Formats         | CSV, TXT        |


---

## 👤 Author

**Sevban Tekin-Eksi**   
[GitHub](https://github.com/st3kin)
