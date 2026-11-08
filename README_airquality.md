# 🌍 Global Air Quality Monitor

A Python project that fetches, stores, and visualizes real-time PM2.5 air quality data from multiple cities around the world using the **OpenAQ API** and **SQLite**.

## 📌 Overview

This project compares PM2.5 (fine particulate matter) pollution levels across three major cities:
- 🇯🇵 **Kobe, Japan**
- 🇫🇷 **Paris, France**
- 🇩🇪 **Berlin, Germany**

Data is fetched via the OpenAQ API, stored in a local SQLite database, and visualized using Matplotlib.

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| `requests` | Fetch data from OpenAQ API |
| `sqlite3` | Store and query air quality data |
| `matplotlib` | Visualize PM2.5 trends |

## 📁 Project Structure

```
├── Global_Air_Quality_Monitor.ipynb   # Main Jupyter Notebook
├── air_quality.db                     # SQLite database (auto-generated)
└── README.md
```

## 🚀 How to Run

```bash
# Install dependencies
pip install requests matplotlib jupyter

# Launch notebook
jupyter notebook Global_Air_Quality_Monitor.ipynb
```

> ⚠️ You need an OpenAQ API key. Get yours free at [openaq.org](https://openaq.org)

## 📊 What It Does

### 1. Fetch Nearby Sensors
Finds PM2.5 sensors within 25km of each city center using coordinates:
- Kobe: `34.69, 135.50`
- Paris: `48.86, 2.35`
- Berlin: `52.52, 13.40`

### 2. Store in SQLite Database
```sql
CREATE TABLE air_quality (
    city TEXT,
    date TEXT,
    pm25 REAL
)
```
100 data points per city stored locally.

### 3. Visualize & Compare
Side-by-side PM2.5 trend comparison across all three cities.

![Air Quality Comparison](figures/comparison.png)

## 📈 Key Findings

| City | Avg PM2.5 (µg/m³) | WHO Safe Limit |
|------|-------------------|---------------|
| Kobe | ~7.5 | 15 µg/m³ |
| Paris | ~14.2 | 15 µg/m³ |
| Berlin | ~10.8 | 15 µg/m³ |

Kobe shows consistently cleaner air compared to European cities.

## 🌐 About

Developed as part of personal research into environmental data analysis using Python.

**Author:** Mohamed Osama  
**Institution:** Kobe University, Faculty of System Informatics  

## 📄 License

MIT License
