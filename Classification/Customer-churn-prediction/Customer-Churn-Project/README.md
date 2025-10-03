
![Alt Text](./Images/pexels-expect-best-79873-351264.jpg)



### Business Problem

**Customer Churn Analysis: A First Data Exploration and Preprocessing Project**

This project is part of my coursework at CodeOp, where I analyze and preprocess customer churn data from a consumer credit card portfolio. The objective is to support a business manager focused on reducing customer attrition by identifying data patterns that may explain why customers are leaving. Though I've worked on other personal projects, this is my first real-world data analysis project within the boot camp. It marks a significant step in my learning journey at CodeOp and showcases my growing skills in data science.



### **Objective of this Project** :

In this initial exploratory data analysis (EDA) project, my focus is to uncover insights that could help the manager identify key factors driving customer churn. Therefore, the analyses and resulting insights aim to:

- Identify and address data quality issues.
- Conduct an initial analysis to reveal trends, patterns, and potential drivers of customer churn.
- Prepare a clean, well-structured dataset for future modeling work.



### **Data Property & Source** :

- Source: [Kaggle: Bank Churn Data Exploration And Churn Prediction](https://www.kaggle.com/code/thomaskonstantin/bank-churn-data-exploration-and-churn-prediction/input)

- Fields:
Here's an explanation of what each of these fields typically signifies in a customer churn dataset:

   - **CLIENTNUM**: This is the unique identifier for each customer. 

    - **Attrition_Flag**: This field indicates whether a customer has churned or is still active. 

    - **Customer_Age**: This field provides the age of the customer. 

    - **Gender**: The customer's gender (often categorized as male or female).

    - **Dependent_count**: The number of dependents the customer has, which can be an indicator of family size or financial responsibility.

    - **Education_Level**: The customer's highest level of education.

    - **Marital_Status**: The customer’s marital status.

    - **Income_Category**: The customer's income bracket.

    - **Card_Category**: The type or tier of the credit card held by the customer (e.g., blue, silver, gold, platinum).

    - **Months_on_book**: The total number of months the customer has been with the credit card company, which is a measure of customer tenure.

    - **Total_Relationship_Count**: The total number of products or accounts the customer has with the bank, reflecting engagement level.

    - **Months_Inactive_12_mon**: The number of months in the past year in which the customer had no transaction activity.

    - **Contacts_Count_12_mon**: The number of times the customer contacted customer service in the past year.

    - **Credit_Limit**: The maximum amount of credit available to the customer.

    - **Total_Revolving_Bal**: The total balance that rolls over to the next billing period, rather than being paid off, indicating the level of credit dependency.

    - **Avg_Open_To_Buy**: The average amount available for purchases, based on the credit limit minus the revolving balance, which shows available credit.

    - **Total_Amt_Chng_Q4_Q1**: The percentage change in transaction amount between the fourth and first quarter.

    - **Total_Trans_Amt**: The total dollar amount of transactions made by the customer over a certain period.

    - **Total_Trans_Ct**: The total number of transactions the customer made over a certain period.

    - **Total_Ct_Chng_Q4_Q1**: The percentage change in the number of transactions between the fourth and first quarters.

    - **Avg_Utilization_Ratio**: The average utilization of the customer’s credit limit, calculated as the revolving balance divided by the credit limit, which is often a predictor of credit risk.

    - **Naive Bayes Classifier Fields**:

    The last two fields are outputs from a Naive Bayes classifier model. They indicate the likelihood or classification based on certain factors related to attrition


### **Business Questions and Analysis Plan** :


1. **How are customers distributed across different demographics?** (*Customer Demographic Segmentation* )

   - **Objective**: Get a clearer picture of the customer segments 

   

2. **What is the demograph of the inactive users and how constituted the major reaosn fo their attrition?** (*Understanding the inactive users and their demographs*)
    
   - **Objective**: Zoom in on the main segment for the analyses

   2. a. **Could dissatisfaction with customer service be contributing to inactivity?** (*Customer Satisfaction and Service Improvement*)

   - **Objective**:  Assess the relationship between several calls placed across the customer service and the percentage of which are attrited customers.

   

3. **Which inactive customers are high risk and should be excluded and which are worth targeting?** (*High-Risk Customer Identification and Exclusion*)

  - **Objective**: Identify high-risk customers based on the use of their credit limit. An ideal measurement will be: avg_use > credit_limit - (credit_limit * 0.30) or where the avg_utilization_ration < 30 (*Standard practice is to not use more than 30% of the credit limit*)

     

4. **How can we ensure we retain our most engaged customers?** (*Retention of Highly Engaged Customers*)

    - **Objective**: Identify the services our existing customers are engaged with. How can we ensure we keep them constantly engaged based on their demographics- so we do not lose them?
 

##### Based on the question, the libraries used were: Pandas, Numpy, Seaborn, Matplotlib

--------------------------------------

### **Insights from the Analyses**:


##### 1. **How are customers distributed across different demographics?** 

   - **Income Distribution:** The customer base is segmented into three primary income categories: low, middle, and high-income earners. Most of the low-income customers are more dependent on their credit cards, showing a higher credit utilization rate. Middle-income earners show varied behavior with age groups using credit differently. High-income earners, especially those aged 61-70, are generally less reliant on credit and rarely use their cards.  

   - **Marital Status & Dependents:** A large proportion of attrited customers are married with 2-3 dependents. This demographic tends to be in the higher income categories but also shows similar financial responsibilities to existing customers.

   - **Education & Attrition:** The data suggests that attrited customers are generally less educated and belong more heavily to the low-income group. Existing customers in the middle-income and high-income categories have higher educational backgrounds. 

##### 2. **What are the demographics of the inactive users and how constituted the major reason for their attrition?** 

   - **Inactive User Demographics:** Inactive users are distributed across various age groups and income categories. Both low and middle-income earners have substantial numbers of inactive users. However, the high-income earners show a larger portion of customers who have been inactive, particularly in the age range of 61-70.  
   - **Reasons for Attrition:** The primary reasons for attrition appear to be account closures and potential dissatisfaction with customer service, as the data reveals that attrited customers tend to contact customer service multiple times (averaging 3 contacts). However, despite reaching out, these customers were not satisfied with the support they received, which could have contributed to their decision to leave.  

##### **Could dissatisfaction with customer service be contributing to inactivity?** 

   - **Yes, dissatisfaction with customer service played a significant role.** Customers who had multiple interactions with customer service but still chose to leave could indicate frustration or unresolved issues, leading to their attrition. A detailed analysis of customer service interactions can provide more insight into specific pain points that need addressing.  

##### 3. **Which inactive customers are high risk and should be excluded and which are worth targeting?** 

   - **Identifying High-Risk Customers:** To identify high-risk customers, we used the credit utilization ratio, where an ideal utilization ratio should be below 30% of the credit limit. Customers exceeding this threshold are at risk of defaulting or being financially overburdened.  

   - **Excluding High-Risk Customers:** Most low-income earners and some middle-income earners have utilization ratios above 30%, signaling over-reliance on credit. These customers were excluded from re-engagement efforts.

   - **Targeting Potentially Retained Customers:** Customers with lower utilization ratios and those with a consistent usage pattern that does not exceed the ideal threshold are worth targeting for retention. These customers are likely more responsible and could be nurtured with rewards or loyalty programs.  

##### 4. **How can we ensure we retain our most engaged customers?** 

   - **Engaged Customers:** Existing customers with good credit utilization patterns (below the 30% threshold) and consistent use of services should be prioritized for retention. This group includes middle-income and high-income earners, particularly those in the age group of 31-60, who show more responsible credit usage.  
   - **Targeted Retention Strategies:** To retain these highly engaged customers, personalized marketing strategies can be employed based on their demographic characteristics. For example:  

     - **Young Adults (14-25):** Engage with financial literacy programs, influencer-led campaigns, or events to create brand loyalty.  
     - **Middle-Aged Adults (26-40):** Offer content around homeownership, investments, and tailored financial advice.  
     - **Older Adults (40+):** Focus on retirement planning, healthcare, and financial security.  
   - **Customer Service Engagement:** Ensuring quick and efficient customer service interactions for high-engagement customers is critical. Personalized customer support can significantly increase satisfaction and reduce the likelihood of churn.  

---

### **General Recommendation and Actions to the Business Manager:**

- 📞**Customer Service Improvements:** Focus on continuous service enhancements and customer experience. Attrited customers had multiple interactions with customer service (averaging 3 contacts) but did not receive satisfactory resolutions, leading to their decision to leave. The KPI for customer service should reflect retaining customers and a course to re-orientate them on how to better manage issues from customers- _for the HR department._
 
- 🚫 **High-Risk Exclusion & Targeting:** Customers who regularly exceed the 30% credit utilization threshold were excluded from re-engagement efforts to help the marketing team focus on this set for customer reactivation. _for the HR department._

- 🔄 **Retention Strategy:**  We have some existing customers whose months of inactivities are the same as those attrited. To retain existing customers- we can achieve this by providing personalized offers and targeted financial products based on their demographic needs and credit usage patterns. The data showed that services 3-5 were mostly used. Where these numbers are indicative of encoded services- we may want to double down on these services as our selling points. However, where these numbers are the frequency of the services- we may have to get the data from the product team to know for a fact which services fall within these frequency counts. _for the HR department._


