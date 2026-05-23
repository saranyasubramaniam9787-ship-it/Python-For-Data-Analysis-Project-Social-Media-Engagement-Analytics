#Social-Media-Engagement-Analytics
This project analyzes social media engagement to identify which content types and strategies generate the highest audience interaction and improve social media performance.


📖 Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools & Technologies](#tools--technologies)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [How to Use](#how-to-use)

## 📊 Project Overview

This project analyzes social media engagement patterns across different content types, categories, and audience demographics. The primary goals were:

- Evaluate engagement metrics (likes, comments, shares, engagement rate) across post types
- Analyze relationships between content attributes and audience engagement
- Identify which post types and strategies generate highest engagement
- Compare performance differences based on content type, country, sentiment, and user demographics
- Derive actionable insights for optimizing social media strategy

**Business Problem:** Social media managers need data-driven insights to maximize audience engagement across platforms. Understanding what content works, when to post, and which audiences engage most helps optimize limited marketing resources.

## 🗂️ Data Source

| Property | Description |
|----------|-------------|
| **Dataset Name** | Social Media Engagement Dataset |
| **Sample Size** | 5,000 records |
| **Domain** | Social Media Analytics / Digital Marketing |
| **Source** | Synthetic dataset generated for analysis (GitHub repository) |

**Key Variables Include:**
- Post attributes: `post_type`, `post_category`, `sentiment`, `hashtags`
- Engagement metrics: `likes`, `comments`, `shares`, `watch_time_sec`, `impression_count`, `engagement_rate`
- Demographics: `age`, `gender`, `country`
- Contextual data: `device_type`, `is_verified`, `posted_at`

## 🛠️ Tools & Technologies

| Category | Tools/Libraries |
|----------|-----------------|
| **Language** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Environment** | Google Colab / Jupyter Notebook |
| **Version Control** | Git & GitHub |

## 🧹 Data Cleaning & Preparation

### Initial Setup
```python
import pandas as pd
df = pd.read_csv("social_media_engagement_5000.csv")
df['posted_at'] = pd.to_datetime(df['posted_at'])

Missing Value Handling
Column	Method Applied
age	Filled with median value, converted to integer
gender	Filled with mode (most frequent value)
likes	Filled with median value, converted to integer
comments	Filled with median value, converted to integer
shares	Filled with median value, converted to integer
sentiment	Filled with mode (most frequent value)
Data Formatting
Standardized post_type and post_category using .str.capitalize()

Capitalized device_type and sentiment using lambda functions

Converted all categorical columns to consistent string format

Duplicate Handling
Checked for duplicates in post_id column

Removed duplicate entries using drop_duplicates(subset='post_id')

Outlier Treatment (Engagement Rate)
Calculated Q1 (25th percentile) and Q3 (75th percentile)

Computed IQR = Q3 - Q1

Defined bounds: Q1 - 1.5×IQR and Q3 + 1.5×IQR

Removed outliers outside bounds (improved skewness)

Feature Engineering
New Field	Formula/Method
Hashtag Count	Split hashtags string and count words
Engagement Score	likes + comments + shares
Day Name	Extracted from posted_at using .dt.day_name()
🔍 Exploratory Data Analysis (EDA)
Key Questions Explored
Question	Analysis Method
Which post types generate highest engagement?	GroupBy mean engagement rate by post_type
How do content categories compare?	Average Engagement Score by post_category
Which countries have most active users?	Average engagement rate by country
What is the impact of demographics?	Age vs Engagement Score analysis
Does verification status matter?	Verified vs non-verified account comparison
When is the best time to post?	Day-wise impression analysis (extracted from posted_at)
How does device type affect watch time?	Average watch time by device_type
Does sentiment drive engagement?	Sentiment vs Engagement Score analysis
Key Visualizations Performed
Correlation matrix for numeric fields (likes, comments, shares, impressions, followers, engagement_rate)

Categorical distribution analysis for gender, country, post_type, post_category, device_type, sentiment

GroupBy summaries for average likes by post type, impressions by country, engagement rate by device type

💡 Key Insights
Content Performance Insights
1. Image posts dominate engagement rates

Post Type	Average Engagement Rate
Image	29.4% (Highest)
Text	Moderate
Video	Moderate
Reel	Moderate
2. Food, Music, and Travel are top-performing categories

Rank	Category	Engagement Score
1	Food	Highest
2	Music	Very High
3	Travel	Very High
4	Fitness	Moderate
5	Fashion	Moderate
Audience & Geographic Insights
3. Germany leads in engagement rate

Rank	Country	Engagement Rate
1	Germany	Highest
2	Canada	Strong
3	Japan	Strong
4	India	Moderate
5	USA	Moderate
6	France	Lowest
4. Age 49 and teenagers show highest engagement scores

Age 49: Highest engagement score

Teenagers: Strong engagement

Users in 30s: Strong engagement

Middle-aged groups: Lower engagement

5. Non-verified accounts outperform verified accounts

Non-verified accounts achieved higher average engagement scores

Suggests authenticity matters more than verification status

Behavioral Insights
6. Tuesday is the best day for impressions

Rank	Day	Average Impressions
1	Tuesday	Highest
2	Saturday	Strong
3	Sunday	Strong
4	Thursday	Lowest
7. Mobile users drive highest watch time

Mobile: Highest average watch time

Tablet: Moderate

Desktop: Lowest average watch time

Sentiment Analysis
8. Emotionally charged content drives engagement

Sentiment	Engagement Score
Positive	Highest
Negative	Strong
Neutral	Lowest
9. Negative posts generate more shares than neutral posts

Negative posts received more likes and shares

Emotional intensity attracts greater attention, even when negative

🚀 Recommendations
Recommendation	Rationale
Prioritize Image and Reel content	These formats generate the highest engagement rates (29.4% for images)
Schedule posts on Tuesdays and weekends	Peak impression days for maximum content visibility
Optimize content for mobile devices	Mobile users have the highest watch time
Create emotionally engaging content	Positive and negative sentiments drive higher interaction than neutral content
Target Germany, Canada, and Japan	These countries show highest engagement rates
Focus on Food, Music, and Travel categories	Consistently top-performing content categories
Don't rely solely on verification status	Non-verified accounts can achieve higher engagement with quality content
Target age groups 49 and teenagers	Highest engagement scores from these demographics
⚙️ How to Use
Prerequisites
bash
Python 3.7+
pip install pandas numpy matplotlib seaborn
Run the Analysis
Clone the repository

bash
git clone https://github.com/yourusername/social-media-engagement-analytics.git
cd social-media-engagement-analytics
Download the dataset

python
# Run in Python/Colab
import pandas as pd
df = pd.read_csv("https://github.com/GeethaGunasekaran1/Dataset_rep/raw/refs/heads/main/social_media_engagement_5000.csv")
Run the preprocessing script

python
# Copy the code from the Data Cleaning & Preparation section
# Ensure posted_at is converted to datetime
df['posted_at'] = pd.to_datetime(df['posted_at'])
Output Files
File Name	Description
social_media_cleaned_dataset.csv	Final cleaned dataset after preprocessing, outlier treatment, and feature engineering
Notebook Structure
Import libraries and load data

Data cleaning and type conversion

Missing value handling

Outlier treatment

Feature engineering

Exploratory data analysis

GroupBy aggregations

Visualization and insights generation
