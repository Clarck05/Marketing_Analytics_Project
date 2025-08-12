# Marketing Analytics Insights Project

This repository contains the complete analysis of ShopEasy's marketing and customer engagement data. The project aims to diagnose the reasons behind declining conversion rates and customer engagement, providing data-driven recommendations to improve marketing strategies.

---

## **Business Problem**

ShopEasy, an online retail business, has experienced a decline in customer engagement and conversion rates despite significant investments in new marketing campaigns. The marketing and customer experience teams are seeking a comprehensive data analysis to understand campaign effectiveness, customer pain points, and strategic opportunities for improvement.

**Key Challenges:**
- **Reduced Customer Engagement:** A noticeable drop in customer interactions with the website and marketing content.
- **Decreased Conversion Rates:** Fewer website visitors are making purchases.
- **Inefficient Marketing Spend:** High marketing expenses are not generating the expected return on investment.
- **Need for Feedback Analysis:** A necessity to analyze customer reviews to improve products and services.

---

## **Project Goals**

The primary goals of this analysis were defined to address the key business challenges:

- **Increase Conversion Rates:** Identify factors impacting conversion rates and recommend strategies to optimize the sales funnel.
- **Enhance Customer Engagement:** Determine which content types drive the most interaction to inform and improve content strategy.
- **Improve Customer Feedback Scores:** Analyze customer reviews to find common themes and provide actionable insights for service and product improvements.

---

## **Tools & Technologies**

- **SQL:** Used for data cleaning, transformation, and extraction from the database.
- **Python:** Employed for advanced analysis, particularly for performing sentiment analysis on customer reviews using Pandas and NLTK (VADER).
- **Power BI:** Utilized for creating an interactive dashboard to visualize the findings and communicate insights effectively.

---

## **Methodology**

### **1. Data Cleaning and Preparation (SQL)**
Raw data from the `PortfolioProject_MarketingAnalytics` database was cleaned and preprocessed using SQL queries.

Key tasks included:
- **fact_customer_journeys.sql:** Removed duplicate customer journey records and imputed missing Duration values with the daily average.
- **fact_engagement_data.sql:** Standardized the `ContentType` column (e.g., 'Socialmedia' → 'Social Media'), extracted Views and Clicks from a combined column, and filtered out 'Newsletter' data.
- **fact_customer_reviews.sql:** Cleaned the `ReviewText` by removing extra spaces.
- **dim_products.sql & dim_customers.sql:** Created dimension tables for products and customers, including a PriceCategory for products.

---

### **2. Sentiment Analysis (Python)**
Customer reviews were further analyzed using a Python script in a Jupyter Notebook (`Marketing_analytics_insights.ipynb`):

- The script fetches review data from the SQL database.
- It uses the NLTK VADER (Valence Aware Dictionary and sEntiment Reasoner) library to calculate a compound sentiment score for each review text.
- Based on the sentiment score and the original star rating, a custom function categorizes each review into **Positive, Negative, Mixed Positive, Mixed Negative, or Neutral sentiments**.
- The final DataFrame, including sentiment scores and categories, was exported to `fact_customer_reviews_with_sentiment.csv`.

---

### **3. Data Visualization (Power BI)**
The processed data was loaded into Power BI to create a comprehensive dashboard (`project_goals_and_outcomes.pdf`). This dashboard visualizes KPIs and trends related to the project goals.

---

## **Key Insights**

### **Conversion Rates**
- Overall conversion rate: **8.5%**
- Significant seasonal trend: **Highest in January (18.5%)**, lowest in May (4.3%).
- Products like **Ski Boots, Kayaks, and Baseball Gloves** showed exceptionally high conversion rates.

### **Customer Engagement**
- Social media views showed a declining trend, peaking in February and July but falling sharply from August onward.
- Overall click-through rate from engaged users: **15.37%**.
- Blog content was the top performer in driving views.

### **Customer Feedback**
- Average rating: **3.7 out of 5** (below the 4.0 target).
- Sentiment analysis results: **275 positive reviews**, **82 negative reviews**, plus notable "Mixed" category feedback.
- Opportunity to convert ambivalent customers into satisfied ones.

---

## **Actionable Recommendations**

### **To Increase Conversion Rates:**
- Focus on high-performing products (Kayaks, Ski Boots).
- Run seasonal campaigns during peak months and create offers in low-performing months.

### **To Enhance Customer Engagement:**
- Revitalize content strategy with interactive videos and user-generated content.
- Optimize calls-to-action in blogs and social media posts, especially during low-engagement months.

### **To Improve Customer Feedback Scores:**
- Implement a feedback loop to analyze mixed/negative reviews.
- Engage with dissatisfied customers to resolve issues and encourage rating updates.

---
