# RetailNova Inc.: Customer Segmentation and Marketing Optimization  
**Customer Segmentation using KMeans Clustering**

## Table of Contents

1. [Project Background and Overview](#1-project-background-and-overview)  
2. [Goals and Objectives](#2-goals-and-objectives)  
3. [Data Structure and Overview](#3-data-structure-and-overview)  
4. [Exploratory Data Analysis (EDA)](#4-exploratory-data-analysis-eda)  
5. [Data Transformation and RFM Analysis](#5-data-transformation-and-rfm-analysis)  
6. [Clustering and Customer Segmentation](#6-clustering-and-customer-segmentation)  
7. [Results](#7-results)  
    - 7.1 [Non-Outliers](#71-non-outliers)  
    - 7.2 [Outliers](#72-outliers)  
8. [Conclusion](#8-conclusion)

---

## 1. **Project Background and Overview**

RetailNova Inc., a UK-based and registered non-store online retailer, specializes in the sale of unique, all-occasion giftware to wholesale enterprises. Catering to a diverse clientele across industries, the company faces the challenge of optimizing its marketing strategies to improve sales performance and enhance customer engagement.

As the Marketing Analyst for RetailNova Inc., I analysed their extensive transactional dataset and leveraged advanced data analytics techniques to group customers into actionable segments. This segmentation allows the marketing team to implement data-driven campaigns, such as targeted ads for dormant customers, upselling strategies for low-spending but active buyers, and loyalty programs for high-value frequent customers.

The goal is to classify customers into distinct groups based on their purchasing behaviour and develop targeted strategies for each segment to improve customer engagement and increase sales.

---

## 2. **Goals and Objectives**

- **Customer Segmentation**: Leverage RFM analysis and K-means clustering to classify RetailNova Inc.'s customers into actionable groups, providing a comprehensive understanding of purchasing behaviour.
- **Marketing Optimization**: Develop tailored marketing strategies for each segment to enhance customer engagement, improve retention, and drive revenue growth.

---

## 3. **Data Structure and Overview**

**OnlineRetail Dataset**: This dataset contains over **500,000** records and provides comprehensive transactional data for RetailNova Inc., capturing the details of customer purchases and product sales. It includes the following fields:

- InvoiceNo: A unique 6-digit number assigned to each transaction. If the code starts with the letter 'C', it denotes a cancellation.
- StockCode: A unique 5-digit code representing individual products.
- Description: The name or description of each product.
- Quantity: The number of units of each product purchased in a transaction.
- InvoiceDate: The date and time when the transaction occurred.
- UnitPrice: The price of a single product unit, recorded in sterling (£).
- CustomerID: A unique 5-digit identifier assigned to each customer.
- Country: The name of the country where the customer resides.

---

## 4. **Exploratory Data Analysis (EDA)**

To ensure the dataset's accuracy and reliability, several preprocessing steps were conducted:  
- **Handling Missing Values**: Rows with missing customer IDs were removed, as these are critical for customer segmentation.  
  [View Code](https://github.com/FOyelude/Customer-Segmentation-using-KMeans-Clustering/blob/main/Kmeans%20Classification%20project.ipynbL5)  

- **Removing Duplicates**: Duplicate transactions were identified and eliminated to prevent inflation of purchase frequency for certain customers.  

- **Invalid Data Removal**: Null or incomplete transactions were filtered out to ensure the dataset's validity.  

- **Outlier Detection and Removal**: After RFM analysis, customers with abnormal purchasing behaviour (e.g., extremely high-frequency buyers, negative quantities, or returns) were identified as outliers. These were separated for further, specific analysis.  
  [View Code](https://github.com/FOyelude/Customer-Segmentation-using-KMeans-Clustering/blob/main/Kmeans%20Classification%20project.ipynb#L27)

---

## 5. **Data Transformation and RFM Analysis**

**RFM** (Recency, Frequency, Monetary) analysis was used to group customers based on their purchasing patterns.

- **Recency**: Calculated as the number of days since a customer’s last purchase.
- **Frequency**: The number of purchases made by a customer during the observed period.
- **Monetary**: The total revenue a customer has generated.

---

## 6. **Clustering and Customer Segmentation**

Following the RFM analysis, RFM scores were computed by ranking each customer on the three metrics—**Recency**, **Frequency**, and **Monetary**—with higher scores indicating more desirable customer behaviour (i.e., recent, frequent, and high-value buyers). These scores were then used to segment customers into distinct groups.

The segmentation process identified two broad categories:
1. **Non-Outliers**: Customers exhibiting standard purchasing behaviours.
2. **Outliers**: Customers with significantly different behaviours, such as unusually high or low purchase patterns.

To refine these groups further, a **K-means clustering algorithm** was employed:
- **Non-Outliers**: Divided into 3 clusters based on their RFM scores.
- **Outliers**: Divided into 4 clusters to better capture their unique characteristics.

Each segment was characterized by distinct purchasing patterns, allowing for targeted marketing strategies to optimize customer engagement and revenue growth.

---

## 7. **Results**

### 7.1 **Non-Outliers**

#### **Frequent Spenders (Group 0)**

**Characteristics**: These customers purchase frequently, have shopped recently, and contribute high revenue.  
**Objective**: Retain their loyalty and increase lifetime value.

**Recommendations**:  
1. **Personalized Loyalty Program**: Implement a tiered system where customers earn points with every purchase. Offer exclusive perks such as early access to new products, premium customer support, and VIP sales.  
2. **Exclusive Offers**: Provide time-sensitive discounts on their favorite categories, ensuring the promotions feel like insider deals.  
3. **Surprise & Delight**: Strengthen their emotional connection with the brand by offering unexpected rewards, such as free products or special discounts.

---

#### **Occasional Shoppers (Group 2)**

**Characteristics**: These customers shop moderately, have average recency, and spend a moderate amount.  
**Objective**: Increase engagement and average order value.

**Recommendations**:  
1. **Product Bundling**: Offer "frequently bought together" bundles or packages with slight discounts to encourage higher spending per visit.  
2. **Personalized Product Suggestions**: Leverage their purchase history and browsing patterns to recommend products tailored to their preferences.  
3. **Customer Surveys & Feedback**: Conduct surveys to understand their preferences and uncover reasons for less frequent shopping. Use their feedback to enhance product offerings and services.

---

#### **Dormant Potentials (Group 1)**

**Characteristics**: These customers shop infrequently, have not visited recently, and contribute minimal revenue.  
**Objective**: Re-engage them and raise brand awareness.

**Recommendations**:  
1. **Win-Back Campaigns**: Use targeted campaigns with limited-time offers (e.g., "We Miss You! Enjoy 20% Off Your Next Purchase") to incentivize them to return.  
2. **Email Drip Campaigns**: Send personalized email series showcasing new collections, promotions, or changes in your store to rekindle their interest.  
3. **Action-Based Incentives**: Provide small rewards, such as discounts or free shipping, for actions like completing a survey, visiting the website, or engaging with your brand’s content.

---

### 7.2 **Outliers**

#### **1. OUT_Upsell (Group 0)**

**Characteristics:** Customers with moderate visit frequency, and recent activity, but low purchasing power.  
**Objective:** Increase average order value (AOV) through upselling and promotions.

**Recommendations**:  
- **Discount Strategy:** Offer promotions like "Buy One Get One (BOGO)" or bundle deals to encourage higher-value purchases per visit.  
- **Product Recommendations:** Suggest higher-value or complementary items based on purchase history.  
- **Upsell at Checkout:** Implement upsell tactics at checkout by offering discounts on related products before finalizing the purchase.

---

#### **2. OUT_Ads (Group 1)**

**Characteristics:** Infrequent visitors, long absence, low purchasing value, likely one-time customers.  
**Objective:** Re-engage and bring customers back to the store.

**Recommendations**:  
- **Targeted Ads:** Run remarketing campaigns via social media and Google to remind them of your store, highlighting new arrivals or previously viewed products.  
- **Email Campaigns:** Send personalized emails with limited-time offers or reminders to encourage their return.  
- **Reactivation Discounts:** Provide exclusive discounts or free shipping, with a time-sensitive offer to create urgency.

---

#### **3. OUT_Delight (Group 2)**

**Characteristics:** Frequent visitors, recent activity, and high monetary value.  
**Objective:** Retain and reward these high-value customers, fostering loyalty.

**Recommendations**:  
- **Surprise and Delight:** Occasionally send surprise offers (e.g., gifts, special discounts) to show appreciation and strengthen loyalty.  
- **VIP Program:** Offer an exclusive VIP tier with perks such as early access to sales, special previews, or a points-based rewards system.  
- **Personalized Offers:** Tailor promotions based on shopping behaviour to maintain their high purchasing habits.

---

#### **4. OUT_Upsell_Priority (Group 3)**

**Characteristics:** Moderate visit frequency, recent activity, second in both frequency and monetary value to Group 2.  
**Objective:** Increase monetary value through prioritized upselling efforts.

**Recommendations**:  
- **Priority Upselling:** Focus on promoting premium products in their preferred categories, with personalized recommendations.  
- **Exclusive Deals:** Provide targeted promotions like tiered discounts (e.g., spend $50, get 10% off; spend $100, get 20% off).  
- **Early Access to Sales:** Offer early access to sales and promotions, creating a sense of exclusivity and encouraging larger purchases.

---

Below is the **distribution** of the various segments: 

![image](https://github.com/user-attachments/assets/7fc4c539-c7e1-4953-9f24-28c489b880e4)

As seen above, **occasional customers** make up a large portion of the customer base. Converting a significant number of them into **frequent spenders** will greatly boost sales.

## 8. **Conclusion**

This segmentation will allow for targeted marketing strategies that cater to the needs of each customer group. The outliers, who behave significantly different from the majority, were given special focus to either increase their value (via upselling) or re-engage them (via ads and discounts). By implementing these strategies, we expect increased customer retention, higher average order values, and improved overall sales.

This analysis has provided a clear roadmap for personalized customer engagement and highlights the importance of RFM analysis in driving data-driven marketing strategies. 

---
[CLICK HERE](https://github.com/FOyelude/Customer-Segmentation-using-KMeans-Clustering/blob/main/Kmeans%20Classification%20project.ipynb) for the full code
