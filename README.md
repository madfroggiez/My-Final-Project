# My-Final-Project

# Detecting Fraud in Financial Transaction Data 

The purpose of this project is to help organizations such as banks and credit card companies detect fraud in real time. To do this, a dataset compiled from known fraudulent and non-fraudulent transactions is used to identify key components commonly present in past cases of fraud. These components can then be used to identify transactions that are high risk of being fraudulent, giving banks and other organizations alike the opportunity to take steps to reduce future loss.

## Dataset Information:

- Data set name: Fraud Detection Transactions Dataset
- Link: https://www.kaggle.com/datasets/samayashar/fraud-detection-transactions-dataset
- shape: (50000, 21)

## Features:

- Transaction_ID - the unique identifier for each transaction
- User_ID - the unique identifier per user
- Transaction_Amount - the amount of money involved in the transaction
- Transaction_Type - the type of transaction (Online, In-Store, ATM, etc.)
- Timestamp - the date and time of the transaction
- Account_Balance - the user's account balance before the transaction
- Device_Type - device used 
- Location - transaction location
- Merchant_Category - merchant type
- IP_Address_Flag - suspicious IP address
- Previous_Fraudulent_Activity - Number of past fraudulent activities by the user
- Daily_Transaction_Count -count of transactions made by the user that day
- Avg_Transaction_Amount_7d - the user's average transaction amount in the past 7 days
- Failed_Transaction_Count_7d -  count of failed transactions in the past 7 days
- Card_Type - type of card used 
- Card_Age - Age of card
- Transaction_Distance - distance from the user's normal location
- Authentication_Method - method used for authentication
- Risk_Score - Fraud risk score
- Is_Weekend - transaction took place on a weekend
- Fraud_Label - fraud or not 

## Model Conclusions 

### Random Forest Model: 

The top ten features the random forest model identified as being the components best used to identify fraud are:

1. Failed_Transaction_Count_7d
2. 7d_severity                 
3. Amount_to_Balance_Ratio
4. Account_Balance
5. Transaction_Amount
6. user_transaction_avg_diff
7. Transaction_Distance
8. Amount_Diff_from_7d_Avg
9. Avg_Transaction_Amount_7d
10. device_distance_age_risk d


### K-Means Clustering Model:
Using the top five features from the random forests model, the k-means model grouped the transactions into five clusters based on their risk of being fraudulent, ranging from low to high risk. 


**Table of Cluster Profiles (Means):**

| Cluster | Failed_Transaction_Count_7d | 7d_severity | Amount_to_Balance_Ratio | Account_Balance | Transaction_Amount | user_transaction_avg_diff | Transaction_Distance | Amount_Diff_from_7d_Avg | Fraud_Label |
|--------|-----------------------------|-------------|--------------------------|-----------------|--------------------|----------------------------|----------------------|---------------------------|------------|
| 0 | 0.856424 | -0.055024 | -0.149780 | 0.186436 | -0.370773 | 0.351939 | -0.047046 | 0.253072 | 0.496083 |
| 3 | 0.336581 | 9.365815 | 10.371883 | -1.703793 | 1.584432 | -1.486507 | -0.017074 | -0.869228 | 0.389222 |
| 2 | 0.008647 | 0.198522 | 0.274655 | -0.033998 | 1.590271 | -1.505237 | 0.000222 | -1.123761 | 0.300595 |
| 1 | -0.865532 | -0.155392 | -0.108386 | -0.149307 | -0.381186 | 0.359644 | 0.047207 | 0.275124 | 0.155146 |

---

**Risk Ranking:**

1. Cluster 0: Highest risk  
2. Cluster 3: High risk  
3. Cluster 2: Moderate risk  
4. Cluster 1: Lowest risk  

---

**Summary**

The cluster that banks and credit card companies should monitor the most is Cluster 0. This group has the highest fraud rate, making it the highest risk segment.  This cluster is characterized by its elevated failed transaction counts and its extremely low amount to balance ratio. 