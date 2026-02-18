# 🎵 Spotify Tracks Strategic Analysis Dashboard

## 📌 Project Overview

This project presents a comprehensive **Business Intelligence analysis** of over **428,000 Spotify tracks**.

Rather than focusing solely on visualization, the dashboard is designed as a **strategic decision-making tool** for:

- 🎧 Music Producers  
- 🏷️ Record Labels  
- 📈 Marketing Strategists  

It explores global music trends, audio characteristics, audience behavior, and content positioning.

---

## 🛠️ Data Transformation & Cleaning (ETL)

The original dataset required significant preprocessing to ensure analytical accuracy and model efficiency.

### ✔️ Data Preparation Steps

- **Duplicate Removal**  
  Removed duplicate `track_id` records to avoid inflated popularity metrics.

- **Handling Missing Values**  
  Cleaned null values in key analytical columns such as `Genre` and `Popularity`.

- **Column Optimization**  
  Removed redundant internal identifiers to improve model performance.

- **Data Normalization**  
  Standardized audio feature metrics (Energy, Danceability, etc.) to a **0–1 scale** for accurate comparative analysis.

---

## 📊 Dashboard Architecture & Key Insights

### 1️⃣ Key Performance Indicators (KPIs)

| KPI | Value | Insight |
|-----|-------|---------|
| Total Tracks | 428K | Scale of analysis |
| Average Popularity | 35.35 | Benchmark for success |
| Explicit % | 0.09% | Content safety trend |

---

### 2️⃣ Audio Feature Analysis

Using a custom DAX measure (`Avg Audio Feature`), the dashboard visualizes the technical composition of tracks.

**Key Observation:**

- High **Energy (0.64)**  
- Strong **Danceability (0.57)**  

➡️ Indicates that global audiences currently favor **upbeat and rhythm-driven music** over acoustic or mellow styles.

---

### 3️⃣ Genre & Market Trends

- **Top 10 Genre Analysis**
- Strong presence of **World-Music** and **Turkish genres**

📌 Suggests increasing demand for localized and culturally diverse content.

---

### 4️⃣ Popularity vs Duration (Bubble Chart)

This visualization evaluates the **Retention Window Hypothesis**.

📈 Tracks with an average duration of **~3.8 minutes** consistently achieve higher popularity scores.

**Implication:**
> There appears to be an optimal duration sweet spot aligned with listener retention behavior.

---

## 📑 DAX Measures Documentation

### ⏱️ Time Conversion

Converts track duration from milliseconds to minutes:

```dax
Average Duration (Min) =
AVERAGE('dataset'[duration_ms]) / 60000
```

### 📊 Dynamic Popularity Measure

Calculates mean popularity across dynamic filters:

```dax
Average Popularity =
AVERAGE('dataset'[popularity])
```

### 📉 Ratio Analysis (Explicit Content)

Determines the percentage of explicit tracks:

```dax
Explicit Percentage =
DIVIDE(
    CALCULATE(COUNTROWS('dataset'), 'dataset'[explicit] = TRUE()),
    COUNTROWS('dataset')
)
```

### 🎨 UI Optimization (Styling Helper)

Used to remove default visual backgrounds for a cleaner dark theme:

```dax
Remove BG = "rgba(255, 255, 255, 0)"
```

---

## 💡 Strategic Applications

### 🎧 For Producers
- Target **Energy > 0.60**
- Optimize track duration near **3.8 minutes**

### 📈 For Marketers
- Focus on **G.C.C.** and **World-Music segments**
- Leverage regional engagement patterns

### 🏷️ For Record Labels
- Maintain availability of **Clean versions**
- Low Explicit % suggests broader reach in radio and public distribution channels

---

## 🚀 Technologies Used

- **Power BI** → Data Modeling & Visualization  
- **DAX** → Advanced Calculations & Metrics  
- **Power Query** → ETL & Data Transformation  

---

## 📌 Conclusion

This dashboard demonstrates how structured data analysis can translate raw streaming data into **actionable music industry insights**.

It highlights the importance of:

- Data-driven production decisions  
- Market-aware genre strategy  
- Retention-based track optimization
