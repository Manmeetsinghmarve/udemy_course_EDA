# Project Report: Exploratory Data Analysis of Udemy Courses (Finance & Accounting)

## 1. Introduction

This project undertakes an Exploratory Data Analysis (EDA) of a dataset containing information on Udemy courses, specifically focusing on the "Finance & Accounting" category. The primary objective is to uncover patterns, trends, and relationships within the course data to gain insights into course characteristics, popularity, pricing strategies, and their potential impact on subscriber engagement and ratings.

## 2. Dataset Overview and Preparation

The analysis begins by loading the `udemy_output_All_Finance__Accounting_p1_p626.csv` dataset. Initial steps include:

* **Loading Data**: The dataset is loaded into a Pandas DataFrame.
* **Initial Inspection**: Displaying the first few rows (`df.head()`) and checking data types and non-null counts (`df.info()`) helps in understanding the structure and identifying potential data quality issues.
* **Handling Duplicates**: Duplicate rows are identified and removed to ensure data integrity, resulting in a cleaner dataset for analysis.
* **Feature Engineering**:
    * `created` and `published_time` columns are converted to datetime objects to facilitate time-based analysis.
    * New features like `creation_year`, `creation_month`, `published_year`, and `published_month` are extracted for trend analysis.
    * `price_detail__amount` is converted to numeric type to enable quantitative analysis of course prices.

## 3. Exploratory Data Analysis (EDA)

The EDA section explores various aspects of the Udemy courses:

### 3.1 Distribution of Course Types (Paid vs. Free)

* **Observation**: The analysis of `is_paid` column (likely through a `value_counts()` and visualization) shows the proportion of paid courses versus free courses. Generally, paid courses are expected to be the majority in a platform like Udemy.
* **Insight**: Understanding this distribution helps in gauging the platform's primary business model for this category.

### 3.2 Subscriber and Rating Analysis

* **Number of Subscribers**: Analyzing the `num_subscribers` distribution (e.g., histogram or descriptive statistics) reveals that a large number of courses have relatively few subscribers, while a select few courses attract a very high number of subscribers, indicating a power-law distribution.
* **Average Rating**: The `avg_rating` and `avg_rating_recent` columns provide insights into course quality. Visualizations (e.g., histograms or density plots) help understand the distribution of ratings, likely skewed towards higher ratings for successful courses.
* **Relationship between Subscribers/Reviews and Rating**:
    * Plots (e.g., scatter plots with regression lines) exploring the relationship between `num_subscribers` and `avg_rating`, and `num_reviews` and `avg_rating`, are crucial.
    * **Insight**: It's generally observed that courses with higher numbers of subscribers and reviews tend to have higher average ratings, suggesting a correlation between popularity, engagement, and perceived quality. This might also indicate a "rich-get-richer" phenomenon where popular courses attract more attention and maintain high ratings.

### 3.3 Top Courses

* Identifying and displaying the top courses based on metrics like `num_subscribers` and `num_reviews` provides examples of highly successful content within the Finance & Accounting domain.
* **Insight**: These top courses can serve as benchmarks for what resonates with the audience, potentially indicating preferred topics, teaching styles, or depth of content.

### 3.4 Temporal Trends in Course Creation and Publication

* **Course Creation Over Time**: Analyzing `creation_year` and `published_year` shows the growth trajectory of course content on the platform. Visualizations (e.g., line plots showing count of courses per year/month) can illustrate periods of significant growth or slowdown.
* **Seasonal Trends**: Breaking down creation/publication by month might reveal seasonal patterns in course development or release strategies.
* **Insight**: This trend analysis helps understand the evolution of the Udemy platform and content supply over time.

### 3.5 Price Analysis

* **Price Distribution**: A histogram or box plot of `price_detail__amount` (for paid courses) reveals common price points and the spread of pricing strategies.
* **Price vs. Subscribers/Ratings**: Exploring the relationship between course price and `num_subscribers` or `avg_rating` is vital.
    * **Insight**: While very low-priced or free courses might attract more subscribers, a positive correlation between price and high ratings could indicate that higher-quality, more comprehensive courses command higher prices and still maintain strong satisfaction.

### 3.6 Impact of Course Structure

* **Number of Lectures**: Analyzing `num_published_lectures` against `num_subscribers` or `avg_rating`.
* **Number of Practice Tests**: Analyzing `num_published_practice_tests` against `num_subscribers` or `avg_rating`.
* **Insight**: These analyses help determine if longer courses or courses with more supplementary materials are perceived as more valuable or attract more learners.

## 4. Conclusion

This EDA on Udemy's Finance & Accounting courses highlights several critical aspects of online learning content:

* The platform hosts a vast number of courses, predominantly paid, with a clear distinction between highly popular courses and the long tail of less subscribed ones.
* Course popularity, as measured by `num_subscribers` and `num_reviews`, strongly correlates with higher `avg_rating`, suggesting that social proof and quality often go hand-in-hand.
* There's been continuous growth in course additions over the years, reflecting the expansion of online education.
* Pricing strategies vary, and while free/low-cost courses attract volume, high-quality, comprehensive courses can command premium prices and still achieve high ratings and substantial enrollment.
* Content structure, such as the number of lectures and practice tests, likely plays a role in perceived value and student engagement.

## 5. Recommendations

Based on this analysis, the following recommendations can be made:

* **For Instructors**: Focus on creating high-quality, comprehensive courses that address niche or high-demand topics. Leverage strong content and student engagement to drive reviews, which in turn can boost visibility and subscriptions. Consider a tiered pricing strategy.
* **For Udemy Platform**: Promote courses with high ratings and engagement to new users. Invest in features that encourage reviews and social sharing for quality courses.
* **For Learners**: Look for courses with a good balance of high subscriber counts, numerous positive reviews, and a clear, well-structured curriculum.

## 6. Future Work

Further analysis could include:

* **Text Analysis (NLP)**: Analyze course titles and descriptions to identify trending topics or keywords.
* **Time Series Forecasting**: Predict future course enrollment trends or pricing effectiveness.
* **Advanced Modeling**: Develop a predictive model to identify features that are most indicative of a course's success (high subscribers, high ratings).
* **Competitor Analysis**: Compare these findings with other online learning platforms to identify unique selling propositions or market gaps.

---
