# 🏠 World Real Estate EDA

A full Exploratory Data Analysis (EDA) on a dataset of **147,000 global real estate listings**, performed using Python and Pandas as part of the Data Analytics Bootcamp at General Assembly.

---

## 📌 Project Overview

This project follows the complete data analytics workflow:

```
Frame → Extract → Wrangle/Prepare → Analyze → Interpret → Communicate
```

The goal is to uncover key drivers of property prices worldwide through data cleaning, feature engineering, and targeted visualizations.

---

## 🧩 Problem Statement

A real estate investor approached our consulting firm seeking **data-driven guidance on global property markets**, with a focus on identifying trends and potential investment opportunities. Three core challenges were identified:

- **Investment Locations** — Determine the most lucrative global markets by analyzing regional trends and market dynamics
- **Property Type Value** — Identify high-value property types to strategically focus on high-return opportunities
- **Pricing Factors** — Investigate the various factors influencing price variations to support optimal investment decisions

---

## 📂 Dataset

- **Name:** World's Real Estate Data (147K listings)
- **Source:** [Kaggle – toriqulstu/worlds-real-estate-data147k](https://www.kaggle.com/datasets/toriqulstu/worlds-real-estate-data147k)
- **File:** `world_real_estate_data(147k).csv`

> ⚠️ To run this notebook, download the CSV from the Kaggle link above and place it in the same directory as the notebook.

---

## 📖 Data Dictionary

| Column | Type | Description |
|--------|------|-------------|
| `title` | str | Listing title (e.g. "3 room apartment 120 m² in Antalya, Turkey") |
| `country` | str | Country where the property is located |
| `location` | str | Full location string (region, city, country) |
| `building_construction_year` | float | Year the building was constructed |
| `building_total_floors` | float | Total number of floors in the building |
| `apartment_floor` | float | Floor level of the specific unit |
| `apartment_rooms` | float | Total number of rooms |
| `apartment_bedrooms` | float | Number of bedrooms |
| `apartment_bathrooms` | float | Number of bathrooms |
| `apartment_total_area` | str → float | Total property area in m² |
| `apartment_living_area` | str → float | Living/usable area in m² |
| `price_in_USD` | float | Listing price in US Dollars |
| `image` | str | URL to listing image (expired) |
| `url` | str | URL to original listing page (expired) |
| `property_type` ⚙️ | str | Engineered: property type extracted from listing title |
| `price_per_sqm` ⚙️ | float | Engineered: price ÷ total area (USD/m²) |
| `building_age` ⚙️ | float | Engineered: 2026 − construction year |

> ⚙️ = feature engineered during the analysis

---

## ❓ Business Questions

1. Which countries have the highest and lowest **median property prices**?
2. Which **property types** are the most expensive on median?
3. Is there a relationship between **living area and price**?
4. Do **newer buildings** cost more than older ones?

---

## 🛠️ Data Cleaning Steps

```
✔ Checked for and removed duplicate rows
✔ Recovered ~130 missing country values by parsing listing titles
✔ Engineered a new `property_type` column extracted from listing titles
✔ Converted area columns from strings (e.g. "120 m²") to float
✔ Removed invalid entries (negative rooms/floors, impossible construction years)
✔ Dropped rows with missing price values
```

---

## ⚙️ Feature Engineering (Bonus)

Two new columns were created to enrich the analysis:

- **`price_per_sqm`** — normalizes price by size for fair cross-country comparison
- **`building_age`** — calculated as `2026 − building_construction_year` to analyze price trends by building age

---

## 📊 Analysis Highlights

- Price distribution histogram
- Listings count by property type and by country (top 15)
- Median price by country — filtered to countries with **100+ listings**
- Median price by property type — filtered to types with **50+ listings**
- Scatter plot of living area vs. price (Pearson correlation: **0.679**)
- Median price grouped by construction decade

---

## 🔍 Key Findings

| Question | Finding |
|----------|---------|
| **Country prices** | Portugal, Italy, and the US have the highest median prices (600K+); Belarus and Georgia are the most affordable |
| **Property type** | Villas lead at ~$775K median — more than double the next category; studios are the most affordable |
| **Area vs. price** | Strong positive correlation (r = 0.679) — larger properties cost significantly more |
| **Building age** | U-shaped pattern: pre-1900s heritage and post-2000 modern builds hold the highest values; 1950s–1960s mid-century homes are the lowest |

---

## 🧰 Tech Stack

```python
Python 3
pandas
jupyter notebook
```

> Visualizations are created using **pandas built-in plotting** (`.plot()`), which uses matplotlib as a backend.

---

## 📁 Project Structure

```
├── project.ipynb                        # Main EDA notebook
├── world_real_estate_data(147k).csv     # Raw dataset (required to run)
└── README.md                            # Project overview (this file)
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# 2. Install dependencies
pip install pandas jupyter

# 3. Launch the notebook
jupyter notebook project.ipynb
```

---

## 🎓 Course Info

**Program:** Data Analytics Bootcamp  
**Institution:** General Assembly  
**Project Type:** Python EDA Individual Project
