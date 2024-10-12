# Customer-Segmentation-using-KMeans-Clustering

#### 1. **Project Overview**
This project aims to perform customer segmentation using RFM (Recency, Frequency, Monetary) analysis on an online retail dataset. The goal is to classify customers into distinct groups based on their purchasing behavior and develop targeted strategies for each segment to improve customer engagement and increase sales.

#### 2. **Dataset Overview**
The dataset contains transaction data from a **real-world online retail business**, including purchase dates, customer IDs, product details, quantity, and monetary value. Each row represents a unique transaction.

---

#### 3. **Data Cleaning**
Before performing any analysis, the dataset was cleaned to ensure accuracy and reliability:
- **Handling Missing Values**: All rows with missing customer IDs were removed since these are essential for customer segmentation.
- **Removing Duplicates**: Duplicate entries were identified and removed to avoid inflating the frequency of purchases for some customers.
- **Outlier Detection and Removal**: Customers with abnormally high or low purchasing behavior (e.g., extremely high-frequency buyers or those with negative order quantities or returns) were considered outliers and treated separately from the rest of the customers.

---

#### 4. **Data Exploration**
Exploratory Data Analysis (EDA) was conducted to understand the distribution of key variables:
- **Recency**: Time since a customer’s last purchase.
- **Frequency**: The number of purchases made by a customer during the observed period.
- **Monetary**: The total revenue a customer has generated.

---

#### 5. **RFM Analysis**
RFM analysis was used to group customers based on their purchasing patterns. The steps included:
- **Recency**: Calculated as the number of days since a customer’s last purchase.
- **Frequency**: The total number of orders placed by each customer.
- **Monetary**: The total amount spent by each customer.

The RFM scores were computed by ranking each customer on these metrics, with the highest rank representing the best behavior (i.e., recent, frequent, and high-value buyers). Customers were then segmented into different groups based on these scores.

---

#### 6. **Clustering and Customer Segmentation**
Two major customer segments were identified: **Non-Outliers** and **Outliers**, with further subgrouping based on their RFM scores.

---

#### 7. **Results**

##### **Non-Outliers**
1. **GROUP 0 ("Frequent Spenders")**  
   - **Characteristics**: Purchase frequently, visit recently, bring in high revenue.  
   - **Recommendations**: Loyalty programs, exclusive offers, personalized upsells.
   
2. **GROUP 1 ("Dormant Potentials")**  
   - **Characteristics**: Don’t visit frequently, haven't been here recently, contribute little revenue.  
   - **Recommendations**: Re-engagement campaigns, win-back promotions, awareness campaigns.

3. **GROUP 2 ("Occasional Shoppers")**  
   - **Characteristics**: Visit moderately, average recency, and average revenue.  
   - **Recommendations**: Tailor product recommendations, product bundling, conduct customer surveys.

##### **Outliers**
1. **OUT_Upsell (Group 0)**  
   - **Characteristics**: Visit moderately, been here recently, low purchasing power.  
   - **Recommendations**: BOGO offers, discount strategies, upselling.

2. **OUT_Ads (Group 1)**  
   - **Characteristics**: Haven’t been here for a long time, low monetary value, likely one-time customers.  
   - **Recommendations**: Run targeted ads and re-engagement campaigns, offer reactivation discounts.

3. **OUT_Delight (Group 2)**  
   - **Characteristics**: Come frequently, bring in the best monetary value.  
   - **Recommendations**: Reward with exclusive perks, VIP programs, surprise and delight initiatives.

4. **OUT_Upsell_Priority (Group 3)**  
   - **Characteristics**: Come moderately frequently, second-best recency and monetary value.  
   - **Recommendations**: Focus on upselling high-end products, offer exclusive deals, early access to promotions.

---

#### 8. **Conclusion**
This segmentation will allow for targeted marketing strategies that cater to the needs of each customer group. The outliers, who behave significantly different from the majority, were given special focus to either increase their value (via upselling) or re-engage them (via ads and discounts). By implementing these strategies, we expect increased customer retention, higher average order values, and improved overall sales.

This analysis has provided a clear roadmap for personalized customer engagement and highlights the importance of RFM analysis in driving data-driven marketing strategies.

