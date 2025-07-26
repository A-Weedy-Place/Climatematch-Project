# 📈 Climate Variability, Vegetation, and Crop Yield Analysis (1981–2020)

This project investigates the impact of precipitation variability on vegetation health and cereal crop yield across three climatically diverse countries: **Costa Rica**, **Namibia**, and **Bangladesh**.

## 🌍 Regions of Study

- **Costa Rica** – Tropical, ocean-influenced rainfall
- **Namibia** – Semi-arid, drought-prone
- **Bangladesh** – Monsoon-dominated South Asia

---

## 📊 Objectives

1. Detect trends in **extreme precipitation anomalies** (wet/dry spells)
2. Track **vegetation health** using NDVI (Normalized Difference Vegetation Index)
3. Calculate **cereal crop yield** using FAO production and land data
4. Explore **correlations** between climate and agricultural outcomes

---

## 📁 Data Sources

| Data Type         | Source                                      | Details                                |
|------------------|---------------------------------------------|----------------------------------------|
| Precipitation     | CHIRPS (Climate Hazards Group)              | Daily rainfall (0.05° resolution)      |
| Vegetation (NDVI) | NOAA AVHRR Land Bundle (via AWS S3)         | Monthly NDVI with QA masking           |
| Crop Yield        | FAO Cereal Production + Area Harvested      | Yield = Production / Area (t/ha)       |

---

## 🧪 Methodology Summary

- **Extreme Events**:
  - *Dry spell*: ≥30 consecutive days with <0.1 mm rain
  - *Wet burst*: ≥50 mm rainfall over any 3-day window

- **Vegetation Analysis**:
  - Monthly NDVI data on the **1st of each month**
  - Filtered for high quality using **QA flags**
  - Regional mean NDVI extracted per country

- **Cereal Yield**:
  - Computed annually using production & harvested area

- **Analysis & Visualization**:
  - Plotted time series with **regression trend lines**
  - Exported datasets to Excel
  - Generated **correlation matrices** for each country

---

## 📁 Output Files

- `cereal_yield_1980_2021.xlsx` – Annual crop yields
- `ndvi_costa_rica.csv`, `ndvi_namibia.csv`, `ndvi_bangladesh.csv` – Monthly NDVI
- `anomalies.xlsx` – Wet & dry anomalies (frequency per year)
- Visualizations of trends and correlations (saved or shown inline)

---

## 📦 Dependencies

- Python 3.8+
- `xarray`, `pandas`, `matplotlib`, `numpy`, `boto3`, `s3fs`, `tqdm`, `pooch`

Install them using:

```bash
pip install xarray pandas matplotlib numpy boto3 s3fs tqdm pooch
