# Social Media Engagement Analytics

This project analyzes social media engagement to identify which content types and strategies generate the highest audience interaction and improve social media performance.

---

## 📖 Table of Contents

- [📊 Project Overview](#-project-overview)
- [🗂️ Data Source](#️-data-source)
- [🛠️ Tools & Technologies](#️-tools--technologies)
- [🧹 Data Cleaning & Preparation](#-data-cleaning--preparation)
- [🔍 Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)
- [💡 Key Insights](#-key-insights)
- [🚀 Recommendations](#-recommendations)
- [⚙️ How to Use](#️-how-to-use)

---

## 📊 Project Overview

This project analyzes social media engagement patterns across different content types, categories, and audience demographics. The analysis focuses on identifying which content strategies generate the highest audience interaction.

### Objectives
- Evaluate engagement metrics across different post types
- Analyze relationships between content attributes and engagement
- Identify high-performing content strategies
- Compare engagement based on country, sentiment, and demographics
- Generate insights to improve social media performance

### Business Problem
Social media managers need data-driven insights to improve audience engagement and optimize content strategy across digital platforms.

---

## 🗂️ Data Source

| Property | Description |
|----------|-------------|
| **Dataset Name** | Social Media Engagement Dataset |
| **Sample Size** | 5,000 Records |
| **Domain** | Social Media Analytics |
| **Source** | Synthetic Dataset for Analysis |

### Key Variables
- `post_type`
- `post_category`
- `sentiment`
- `likes`
- `comments`
- `shares`
- `watch_time_sec`
- `engagement_rate`
- `country`
- `gender`
- `age`
- `device_type`
- `is_verified`
- `posted_at`

---

## 🛠️ Tools & Technologies

| Category | Tools / Libraries |
|----------|------------------|
| **Programming Language** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Environment** | Google Colab / Jupyter Notebook |
| **Version Control** | Git & GitHub |

---

## 🧹 Data Cleaning & Preparation

### Data Import

```python
import pandas as pd

df = pd.read_csv("social_media_engagement_5000.csv")
df['posted_at'] = pd.to_datetime(df['posted_at'])
```

### Missing Value Handling

| Column | Method Applied |
|--------|----------------|
| age | Filled with median |
| gender | Filled with mode |
| likes | Filled with median |
| comments | Filled with median |
| shares | Filled with median |
| sentiment | Filled with mode |

### Data Formatting
- Standardized categorical values
- Converted date column into datetime format
- Cleaned text columns using string functions

### Duplicate Handling

```python
df.drop_duplicates(subset='post_id', inplace=True)
```

### Outlier Treatment
- Used IQR Method
- Removed extreme values from engagement rate column

### Feature Engineering

| New Feature | Description |
|-------------|-------------|
| Engagement Score | likes + comments + shares |
| Hashtag Count | Total hashtags used |
| Day Name | Extracted from posting date |

---

## 🔍 Exploratory Data Analysis (EDA)

### Analysis Performed
- Engagement rate by post type
- Category-wise engagement comparison
- Country-wise performance analysis
- Sentiment analysis
- Device usage analysis
- Demographic analysis
- Best posting day analysis

### Key Visualizations
- Correlation Heatmap
- Bar Charts
- Pie Charts
- Count Plots
- Box Plots
- Line Charts

---

## 💡 Key Insights

### Content Performance
- Image posts generated the highest engagement rate
- Food, Music, and Travel categories performed best

### Audience Insights
- Germany showed the highest engagement rate
- Teenagers and age 49 users had strong engagement

### Behavioral Insights
- Tuesday generated highest impressions
- Mobile users had the highest watch time

### Sentiment Insights
- Positive sentiment generated highest engagement
- Negative posts received more shares than neutral posts

---

## 🚀 Recommendations

| Recommendation | Reason |
|---------------|--------|
| Focus on Image & Reel content | Higher engagement rates |
| Post on Tuesdays & Weekends | Higher impressions |
| Optimize for Mobile | Highest watch time |
| Use Emotional Content | Better audience interaction |
| Target High-Performing Countries | Better engagement opportunities |

---

## ⚙️ How to Use

### Clone Repository

```bash
git clone https://github.com/yourusername/social-media-engagement-analytics.git
```

### Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn
```

### Load Dataset

```python
import pandas as pd

df = pd.read_csv("social_media_engagement_5000.csv")
```

### Run Notebook
Open the notebook in:
- Google Colab
- Jupyter Notebook

---

## 📁 Output Files

| File Name | Description |
|-----------|-------------|
| social_media_cleaned_dataset.csv | Final cleaned dataset |
| social_media_analysis.ipynb | Complete analysis notebook |

---

## 📌 Conclusion

This project provides valuable insights into social media engagement trends and audience behavior. The findings help optimize content strategy, improve engagement, and support data-driven decision-making for digital marketing.

---

## 👩‍💻 Author

**Saranya**

Data Analytics Project using Python, Pandas, NumPy, Matplotlib, and Seaborn.
