# 🌍 Global Real Estate Market Intelligence Analysis

A full Exploratory Data Analysis (EDA) and market intelligence project analyzing **147,000 global real estate listings across 27 countries** using Python and Pandas.

This project was developed as part of the Data Analytics Bootcamp at General Assembly and focuses on uncovering investment trends, pricing drivers, and high-value real estate opportunities across international markets.

---

# Consultancy Scenario

This project was developed as part of a simulated consulting engagement for a real estate investor seeking data-driven insights into global property markets.

Using over 147,000 international property listings across 27 countries, the analysis focused on:
- Identifying high-value investment markets
- Comparing property types across regions
- Understanding pricing drivers
- Evaluating the impact of building age and property size on valuation

The project combined Python-based exploratory data analysis, feature engineering, and business-focused visual storytelling to support investment decision-making.

---

## 📸 Analysis Preview

### Median Property Prices by Country

![Median Price by Country](images/median-price-country.png)

### Property Type Price Comparison

![Property Type Prices](images/property-type-prices.png)

### Living Area vs Price Correlation

![Area vs Price](images/area-vs-price.png)

> Strong positive relationship identified between property size and listing price (Pearson correlation: 0.679).

### Building Age Analysis

![Building Age Analysis](images/building-age-analysis.png)

---

# 📌 Project Overview

This project follows the complete data analytics workflow:

```text
Frame → Extract → Wrangle/Prepare → Analyze → Interpret → Communicate
```

The goal was to transform raw international property listing data into actionable business intelligence through:
- Data cleaning
- Feature engineering
- Statistical analysis
- Exploratory visualizations
- Market comparison analysis

The analysis focused on uncovering the key drivers behind property valuation and identifying promising investment opportunities worldwide.

---

# 🧩 Business Problem

A real estate investor approached our consulting firm seeking data-driven guidance on global property markets, with a focus on identifying trends and potential investment opportunities.

Three core business challenges were identified:

### Investment Locations
Determine the most lucrative global markets by analyzing regional trends and pricing dynamics.

### Property Type Value
Identify which property categories generate the highest market value and investment potential.

### Pricing Factors
Investigate the factors influencing price variation, including:
- Property size
- Building age
- Property type
- Geographic location

---

# 📂 Dataset

- **Dataset Name:** World's Real Estate Data (147K Listings)
- **Source:** Kaggle
- **Listings:** 147,000+
- **Countries Covered:** 27
- **File:** `world_real_estate_data(147k).csv`

### Dataset Link
https://www.kaggle.com/datasets/toriqulstu/worlds-real-estate-data147k

> ⚠️ To run this notebook, download the CSV file from Kaggle and place it in the same directory as the notebook.

---

# 📖 Data Dictionary

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
| `image` | str | URL pointing to the property listing image (expired) |
| `url` | str | URL pointing to the original property listing page (expired) |
| `property_type` ⚙️ | str | Extracted property type (apartment, villa, studio, etc.) |
| `price_per_sqm` ⚙️ | float | Property price per square meter in USD, calculated as `price_in_USD / apartment_total_area` |
| `building_age` ⚙️ | float | Age of the building in years as of 2026, calculated as `2026 - building_construction_year` |

> ⚙️ = Feature engineered during analysis

---

# ❓ Business Questions

1. Which countries have the highest and lowest median property prices?
2. Which property types are the most expensive?
3. Is there a relationship between living area and price?
4. Do newer buildings cost more than older ones?
5. Which countries provide the strongest balance between affordability and investment potential?

---

# 🛠️ Data Cleaning & Preparation

The dataset required extensive preprocessing before analysis.

### Cleaning Steps Performed

```text
✔ Checked for and removed duplicate rows
✔ Recovered missing country values from listing titles
✔ Converted area-related columns from string to numeric
✔ Removed invalid and impossible values
✔ Standardized numerical columns
✔ Dropped rows with missing price values
✔ Cleaned inconsistent formatting issues
```

---

# ⚙️ Feature Engineering

Several analytical features were engineered to improve the quality of the analysis.

### Engineered Features

#### `property_type`
Extracted from listing titles to classify properties into categories such as:
- Villa
- Apartment
- Studio
- Penthouse
- Chalet
- Condo

#### `price_per_sqm`
Calculated using:

```python
price_in_USD / apartment_total_area
```

This metric normalized pricing across properties of different sizes for fair comparison.

#### `building_age`
Calculated using:

```python
2026 - building_construction_year
```

This enabled age-based market trend analysis.

---

# 🧠 Assumptions & Notes

- Missing country values were inferred from listing titles where possible.
- Area-related columns were converted from string format into numeric measurements.
- Building age calculations were based on the year 2026.
- Some listings contained incomplete metadata and were excluded during cleaning.
- Property type categories were inferred from listing titles using keyword extraction logic.

---

# 📊 Analysis Highlights

The analysis included:

- Median property price by country
- Property type pricing comparison
- Living area vs price correlation analysis
- Building age pricing trends
- Country-level affordability analysis
- Property value distribution analysis
- Price-per-square-meter comparisons

---

# 🔍 Key Findings

## 🌍 Country Price Insights

- Portugal, Italy, and the United States showed the highest median property prices.
- Belarus and Georgia represented the most affordable entry markets for investors.
- Significant price variation exists across global real estate markets.

---

## 🏡 Property Type Insights

- Villas dominated the luxury market with median prices near **$775K**.
- Studios were the most affordable property category.
- Premium property categories showed major price gaps compared to entry-level housing.

---

## 📈 Area vs Price Relationship

- Strong positive correlation identified between living area and listing price.
- Pearson correlation coefficient: **0.679**
- Larger properties consistently commanded higher market valuations.

---

## 🏗️ Building Age Insights

- Modern buildings (post-2000) achieved the highest median prices.
- Mid-century properties showed lower market valuations.
- Some heritage/pre-1900 properties retained strong premium value.

---

# 📌 Strategic Recommendations

- Prioritize newer constructions (post-2000) in high-median-price countries for stronger long-term investment potential.
- Focus on premium property types such as villas and penthouses in competitive markets.
- Approach mid-century properties cautiously due to potential renovation and modernization costs.
- Use price-per-square-meter metrics for fair cross-country property comparison.

---

# 🧰 Tech Stack

```python
Python
Pandas
Matplotlib
Jupyter Notebook
```

### Core Skills Applied

- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Engineering
- Statistical Analysis
- Data Visualization
- Business Insight Generation

---

# 📁 Project Structure

```bash
├── project.ipynb
├── world_real_estate_data(147k).csv
├── images/
│   ├── median-price-country.png
│   ├── property-type-prices.png
│   ├── area-vs-price.png
│   └── building-age-analysis.png
└── README.md
```

---

# 🚀 How to Run

```bash
# Clone repository
git clone https://github.com/your-username/your-repo-name.git

# Navigate into folder
cd your-repo-name

# Install dependencies
pip install pandas matplotlib jupyter

# Launch notebook
jupyter notebook project.ipynb
```

---

# 🎓 Course Information

**Program:** Data Analytics Bootcamp  
**Institution:** General Assembly  
**Project Type:** Python Exploratory Data Analysis (EDA) Project

---

# 👤 Author

**Ebrahim Alsawan**

### Connect With Me
- LinkedIn: https://www.linkedin.com/in/ebrahim-alsawan-a6977a2b9/
