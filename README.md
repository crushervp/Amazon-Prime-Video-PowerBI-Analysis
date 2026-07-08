# Amazon Prime Video Catalog & Quality Analytics Dashboard
[![Power BI](https://img.shields.io/badge/Power_BI-Data_Visualization-yellow?style=flat&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Measures_&_Modeling-blue?style=flat&logo=microsoft&logoColor=white)]()

An enterprise-grade, 3-page Power BI dashboard providing strategic insights into Amazon Prime Video's global streaming catalog. This project transforms raw content metadata into an interactive, application-style visual interface designed for executive-level content strategy and catalog optimization.

## 📊 Dashboard Preview & Deliverables
* **Interactive Power BI File:** `Amazon Prime Video Report.pbix` (Download to explore data models and custom DAX measures)
* **Static Case Study Report:** `Amazon_Prime_Video_Catalog_Analysis.pdf` (Included in repository for quick preview)

---

## 🛠️ Architecture & Technical Stack
* **Data Modeling:** Star Schema design optimized via Power Query by handling multi-valued, comma-separated dimensions (Genres & Credits) into structurally sound relationships.
* **Database Relationships:** Implementation of 1-to-Many bidirectional cross-filtering between core descriptive tables (`titles`) and structural mapping entities (`credits`).
* **UI/UX Paradigm:** Premium application-inspired Dark Theme customized using precise color typography accents matching the signature corporate identity.

---

## 📈 Key Insights & Dashboard Structure

### 1. Executive Summary (Catalog Overview)
* Evaluates the absolute volume and split across the catalog (~10K total titles, heavily dominating with a 9K to 1K ratio in favor of Movies over TV Shows).
* Global geographic mapping detailing market production saturation across major continental territories.
* Dynamic, cross-filtered slicing mechanisms isolating catalog distribution arrays by content certificate ratings and timeline iterations.

### 2. Content Quality & Performance Analysis
* Tracks the historical timeline movement of critical audience assessment values (IMDB/Rotten Tomatoes metrics) across the platform’s lifecycle.
* isolates the top 10 performing catalog genres based on raw weighted performance scores rather than simple content volume.
* Implements an interactive talent leaderboard matrix evaluating core production personnel performance indicators (Title volume vs. Mean Quality Value).

### 3. Catalog Strategy & Optimization
* **The Sweet Spot Matrix:** A custom scatter plot visual tracking the optimization correlation between project runtimes (Duration) and consumer reception scores.
* **Growth Metrics:** Time-series analysis showcasing the post-2010 scaling patterns across high-impact platform content categories.
* **Catalog Risk Management Table:** Actionable intelligence table highlighting underperforming assets with low audience reception to drive tactical content acquisition and licensing removal decisions.

---

## 💡 Key Core DAX Measures Utilized
```DAX
Total Titles = COUNTROWS('titles')

Movie Count = CALCULATE([Total Titles], 'titles'[type] = "Movie")

TV Show Count = CALCULATE([Total Titles], 'titles'[type] = "TV Show")

Avg IMDB Rating = AVERAGE('titles'[imdb_score])
