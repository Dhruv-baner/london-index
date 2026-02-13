# The London Index
A multi-source analysis of London data, aggregated into a composite liveability index

### **🎯 Project Aim**

This project analyzes quality of life and housing affordability across London's 33 boroughs to identify which areas offer the best trade-offs between livability and cost. By combining transport accessibility, crime rates, economic indicators, and property prices, we aim to answer: **"Which London boroughs provide the best value for residents?"**

---

### **📊 Data Sources**

| Source | Data Collected | Access Method |
|--------|---------------|---------------|
| **Transport for London (TfL) API** | 2,646 rail/tube/DLR stations, 621 bus routes with 80,479 stops | REST API |
| **Police.uk API** | 30,774 crime incidents (October 2024) across 14 categories | REST API |
| **UK Land Registry** | 913,320 property transactions (2024), filtered to 103,714 London sales | CSV Download |
| **London Datastore** | Borough boundaries (GIS), population, earnings, jobs density | CSV/GeoJSON/Excel |

---

### **🔧 Collection & Preprocessing**

**Data Collection:**
- Automated API calls for real-time transport and crime data
- Bulk downloads for property prices and economic indicators
- All raw data collected at borough or sub-borough level

**Data Cleaning:**
- Deduplicated 2,646 → 962 unique TfL stations (removed platform duplicates)
- Spatially matched 80k bus stops and 922 stations to borough boundaries using geopandas
- Filtered 913k UK properties → 104k London transactions using county labels
- Parsed multi-sheet Excel files to extract latest year data (2023-2024)

**Feature Engineering:**
- Created composite transport score (60% rail + 40% bus coverage, normalized 0-100)
- Calculated crime rate per 1,000 residents for fair comparison
- Aggregated all metrics to borough level (33 boroughs)

**Final Output:** 
Clean dataset with 33 boroughs × 18 indicators, ready for analysis.

---

*More sections coming soon: Exploratory Analysis, Modeling, Key Findings*
