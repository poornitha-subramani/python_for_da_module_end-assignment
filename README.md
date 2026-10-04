# 📊 Social Media Engagement Analysis Using Python

## 📌 Project Overview

This project focuses on analyzing social media engagement data to identify user behavior patterns, content performance, and engagement trends. Using Python and its data analysis and visualization libraries, the project explores engagement metrics such as likes, comments, shares, impressions, watch time, and engagement rate.

The analysis involves data import, data cleaning, exploratory data analysis (EDA), data wrangling, statistical analysis, and data visualization to generate meaningful insights that can support data-driven content strategies.

## 🎯 Objectives

* Import and inspect a social media engagement dataset.
* Clean missing values, duplicates, inconsistent categories, and unrealistic records.
* Perform exploratory data analysis using Pandas and NumPy.
* Apply data transformation and feature engineering techniques.
* Calculate descriptive statistics and examine relationships between numerical variables.
* Create visualizations using Matplotlib, Seaborn, and Plotly.
* Identify content performance patterns, audience trends, and behavioral insights.
* Summarize findings and derive actionable recommendations.

## 📂 Dataset Information

* **Dataset:** Social Media Engagement Dataset
* **File Name:** `social_media_engagement_5000.csv`
* **Original Records:** 5,000
* **Original Features:** 19
* **Data Format:** CSV

The dataset contains information related to users, posts, engagement metrics, content categories, posting dates, devices, and audience characteristics.

### Key Variables

| Variable         | Description                        |
| ---------------- | ---------------------------------- |
| user_id          | Unique identifier of a user        |
| age              | Age of the user                    |
| gender           | Gender category                    |
| country          | User's country                     |
| post_id          | Unique identifier of a post        |
| post_type        | Type of social media post          |
| post_category    | Content category                   |
| likes            | Number of likes received           |
| comments         | Number of comments received        |
| shares           | Number of shares received          |
| impression_count | Total post impressions             |
| watch_time_sec   | Total watch time in seconds        |
| follower_count   | Number of followers                |
| engagement_rate  | Engagement relative to impressions |
| posted_at        | Date of publication                |
| sentiment        | Sentiment category                 |
| device_type      | Device used                        |
| is_verified      | Verified account status            |
| hashtags         | Hashtags associated with a post    |

## 🛠️ Technologies and Libraries

* **Python** – Core programming language
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations and transformations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical data visualization
* **Plotly Express** – Interactive visualizations
* **Google Colab** – Cloud-based development environment

## 🔍 Task 1: Data Import and Setup

The dataset was imported into Python using Pandas.

### Operations Performed

* Imported the required Python libraries.
* Loaded the CSV file into a Pandas DataFrame.
* Examined data types and column information.
* Converted the posting date column into a datetime format.
* Standardized the verified account column into Boolean values.

### Key Functions

* `pd.read_csv()`
* `df.dtypes`
* `pd.to_datetime()`
* `astype()`
* `df.shape`

## 🧹 Task 2: Data Cleaning

Data cleaning was performed to improve data quality, consistency, and reliability before analysis.

### 2.1 Missing Value Handling

* Identified missing values using `isnull()` and `isna()`.
* Replaced missing numerical values in age, likes, comments, and shares with their respective medians.
* Filled missing gender values using the mode.
* Replaced missing sentiment values with the neutral category.
* Applied forward fill and backward fill to the posting date column.

### 2.2 Duplicate Handling

* Identified complete duplicate records.
* Checked duplicate post identifiers.
* Removed duplicate records using `drop_duplicates()`.
* Reset the DataFrame index after cleaning.

### 2.3 Data Formatting and Standardization

* Standardized categorical values using string methods.
* Removed leading and trailing whitespace.
* Applied consistent capitalization to categorical columns.
* Converted verified account indicators into Boolean values.

### 2.4 Unrealistic Value Handling

* Removed negative likes, comments, and shares.
* Restricted user age to a reasonable range of 13–100 years.
* Checked whether total interactions exceeded impressions.
* Removed records that violated the selected engagement constraints.
* Recalculated engagement rate after handling missing values.

### 2.5 Feature Cleaning

* Extracted hashtag counts from the hashtags column.
* Replaced empty and missing sentiment labels with Neutral.
* Reset the DataFrame index after filtering.

## 📈 Task 3: Exploratory Data Analysis (EDA)

Exploratory data analysis was performed to understand the dataset's structure, distributions, and relationships.

### 3.1 Dataset Inspection

* Displayed the first and last records using `head()` and `tail()`.
* Checked dataset dimensions using `shape`.
* Inspected column names using `columns`.
* Examined data types and non-null counts using `info()`.
* Generated descriptive statistics using `describe()`.

### 3.2 Categorical Analysis

Analyzed the distribution of the following categorical variables:

* Gender
* Country
* Post type
* Post category
* Device type
* Sentiment

Functions used:

* `value_counts()`
* `unique()`
* `nunique()`

### 3.3 Correlation Analysis

Created a correlation matrix for numerical variables to examine relationships between:

* Age
* Likes
* Comments
* Shares
* Watch time
* Impressions
* Followers
* Engagement rate
* Hashtag count

### 3.4 Grouped Analysis

Performed grouped summaries to examine:

* Average likes by post type.
* Total impressions by country.
* Engagement metrics by post type.
* Engagement metrics by country.
* Engagement metrics by sentiment.

Functions used:

* `groupby()`
* `mean()`
* `sum()`
* `round()`

## 🔄 Task 4: Data Wrangling and Feature Engineering

Data wrangling was performed to create additional analytical variables and prepare the dataset for deeper analysis.

### 4.1 Feature Engineering

Created the following features:

| Feature          | Description                                           |
| ---------------- | ----------------------------------------------------- |
| engagement_score | Weighted combination of likes, comments, and shares   |
| log_impressions  | Log-transformed impression count                      |
| log_likes        | Log-transformed likes                                 |
| day_of_week      | Day of the week when a post was published             |
| month            | Month of publication                                  |
| hashtag_count    | Number of hashtags in a post                          |
| country_avg_er   | Average engagement rate for the corresponding country |

### 4.2 Engagement Score

Calculated a weighted engagement score using:

**Engagement Score = Likes + (2 × Comments) + (3 × Shares)**

This formula assigns greater weight to comments and shares to represent their relative contribution to the chosen engagement scoring model.

### 4.3 Log Transformation

Applied `np.log1p()` to impressions and likes to reduce the influence of highly skewed values and support further analysis.

### 4.4 Date-Based Features

Extracted:

* Day of the week
* Month of publication

These features can support time-based engagement analysis.

### 4.5 Data Merging and Grouping

* Calculated average engagement rate by country.
* Merged the country-level average engagement rate back into the original dataset.
* Grouped and summarized engagement metrics by post type, country, and sentiment.

Functions used:

* `groupby()`
* `merge()`
* `rename()`
* `np.log1p()`
* `dt.day_name()`
* `dt.to_period()`

## 📊 Task 5: Statistical Analysis

Descriptive statistical methods were used to summarize numerical variables and understand their distributions.

### Statistical Measures

| Measure            | Purpose                                         |
| ------------------ | ----------------------------------------------- |
| Mean               | Measures the arithmetic average                 |
| Median             | Identifies the middle value                     |
| Mode               | Identifies the most frequent value              |
| Standard Deviation | Measures data dispersion                        |
| Variance           | Measures squared deviations from the mean       |
| Percentiles        | Describe the distribution at selected positions |
| Skewness           | Measures distribution asymmetry                 |
| Kurtosis           | Describes distribution tail characteristics     |

### Variables Analyzed

* Likes
* Comments
* Shares
* Watch time
* Engagement rate
* Follower count

### Statistical Techniques

* Calculated mean, median, standard deviation, and variance.
* Identified the mode for each numerical variable.
* Calculated the 25th, 50th, 75th, and 90th percentiles.
* Examined skewness and kurtosis.
* Generated a correlation matrix to explore numerical relationships.

The statistical summaries provide a foundation for comparing engagement patterns and identifying variables that may be associated with stronger content performance.

## 📉 Task 6: Data Visualization

Visualizations were created using Matplotlib, Seaborn, and Plotly Express to explore the dataset and communicate analytical findings.

### 6.1 Matplotlib Visualizations

* **Scatter Plot:** Examined the relationship between impressions and likes.
* **Line Plot:** Visualized average daily engagement score.
* **Bar Chart:** Displayed the distribution of posts by category.
* **Pie Chart:** Illustrated gender distribution.
* **Histogram:** Examined the age distribution of users.
* **Box Plot:** Identified the spread and potential outliers in engagement rate.

### 6.2 Seaborn Visualizations

* **Count Plot:** Compared the frequency of different post types.
* **Bar Plot:** Compared average likes across post categories.
* **Violin Plot:** Examined follower count distributions across sentiment categories.
* **Pair Plot:** Explored pairwise relationships between selected numerical variables.
* **Heatmap:** Visualized the correlation matrix.
* **Swarm Plot:** Examined engagement rate distributions across device types using a sample of records.

### 6.3 Interactive Plotly Visualizations

* **Bubble Scatter Plot:** Explored impressions versus likes, with bubble size representing shares and color representing post type.
* **Interactive Line Chart:** Visualized daily average engagement scores.
* **Interactive Bar Chart:** Compared average engagement rates across countries.

These visualizations help identify patterns, compare categories, and communicate findings more effectively.

## 💡 Final Insights and Business Analysis

The following questions guide the interpretation of the analysis. The final conclusions should be based on the actual cleaned dataset outputs and visualizations.

### 1. Content Performance

**Post Type with the Highest Engagement**

* Compare average engagement score and engagement rate across post types.
* Identify which post format performs best based on the selected engagement measure.

**Best Performing Content Category**

* Compare likes, comments, shares, and engagement rates across content categories.
* Identify categories that attract higher audience interaction.

**Countries with the Highest Average Engagement Rate**

* Compare country-level average engagement rates.
* Identify countries with stronger engagement in the dataset.

### 2. User Trends

**Effect of Age on Engagement**

* Examine the relationship between age and engagement metrics.
* Use correlation analysis and age-based group comparisons to identify possible patterns.

**Verified vs. Non-Verified Account Performance**

* Compare engagement rates, impressions, and interactions for verified and non-verified accounts.
* Identify differences in the observed performance of the two groups.

### 3. Behavioral Insights

**Best Time of Day for Impressions**

* Examine impressions across posting times if the dataset contains reliable time-of-day information.
* If only posting dates are available, analyze daily or weekday trends instead.
* Avoid drawing conclusions about the best posting hour without time-of-day data.

**Impact of Device Type on Watch Time**

* Compare average watch time across device types.
* Explore whether the observed watch-time distributions differ between devices.

### 4. Sentiment Analysis

**Best Performing Sentiment**

* Compare average engagement metrics across sentiment categories.
* Identify which sentiment group has the highest observed engagement.

**Negative and Neutral Sentiment Behavior**

* Compare likes, comments, shares, impressions, and engagement rates for negative and neutral posts.
* Examine whether these sentiment groups exhibit different engagement patterns.

## 📌 Key Findings

Complete this section after reviewing the actual analysis outputs.

* **Top-performing post type:** [Insert result]
* **Best-performing content category:** [Insert result]
* **Country with the highest average engagement rate:** [Insert result]
* **Age group with the highest engagement:** [Insert result]
* **Verified account performance:** [Insert result]
* **Best-performing sentiment:** [Insert result]
* **Device type with the highest average watch time:** [Insert result]
* **Most important numerical relationship:** [Insert result]

## 🚀 Business Recommendations

Based on the findings from the analysis, the following recommendations can be considered:

* Prioritize content formats that demonstrate consistently high engagement.
* Develop content strategies around categories that attract stronger audience interaction.
* Adapt content strategies to country-level audience behavior.
* Use age-related engagement patterns to guide audience segmentation.
* Evaluate verified and non-verified account performance using comparable engagement metrics.
* Optimize posting schedules only when reliable time-based data is available.
* Explore device-specific content improvements when watch-time differences are observed.
* Use sentiment-related engagement patterns to guide content planning.
* Monitor engagement metrics regularly to evaluate content performance over time.

These recommendations should be refined according to the actual findings rather than assumed patterns.

## 🧠 Skills Demonstrated

* Python Programming
* Data Import and Export
* Data Cleaning and Preprocessing
* Missing Value Treatment
* Duplicate Detection and Removal
* Data Type Conversion
* Exploratory Data Analysis
* Data Wrangling
* Feature Engineering
* Descriptive Statistics
* Correlation Analysis
* Grouped Data Analysis
* Data Visualization
* Statistical Interpretation
* Business Insight Generation

## 📁 Project Structure

```text
Social-Media-Engagement-Analysis/
│
├── social_media_engagement_5000.csv
├── social_media_engagement_analysis.ipynb
└── README.md
```

## 🏁 Conclusion

This project demonstrates an end-to-end Python-based data analysis workflow using a social media engagement dataset. Through data cleaning, exploratory data analysis, feature engineering, descriptive statistics, and visualization, the project provides a structured approach to understanding content performance and audience engagement.

The analysis also demonstrates how Python can be used to transform raw data into interpretable findings that support data-driven decision-making.

**Project Status:** Completed — Analysis and visualizations executed; final insights to be documented using the observed results.

