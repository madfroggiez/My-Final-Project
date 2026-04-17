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
    -  Count of failed transactions during a 7 day period
2. Transaction_Distance
    - Distance from the user's usual location
3. Account_Balance
    - Balance of the user's account before the transaction took place
4. Avg_Transaction_Amount_7d
    - Average transaction amount during a seven day period
5. Amount_Deviation_from_7d_Avg
    - Difference between the 7-day average and the current transaction amount
6. Transaction_Amount
    - Amount spent during the transaction
7. Amount_to_Balance_Ratio
    - Ratio of the amount spent in the transaction to the account balance
8. Card_Age
    - Age of the card
9. Daily_Transaction_Count
    - Number of transactions completed on the day the transaction took place
10. Is_Weekend
    - Indicates whether the transaction took place on a weekday or not

### K-Means Clustering Model:
Using the top five features from the random forests model, the k-means model grouped the transactions into five clusters based on their risk of being fraudulent, ranging from low to high risk. 


**Table of Cluster Profiles (Means):**
| Cluster | Failed Transaction Count 7d | Transaction Distance | Account Balance | Avg Transaction Amount 7d | Amount Deviation from 7d Avg | Fraud Label |
|--------|-----------------------------|----------------------|-----------------|---------------------------|------------------------------|------------|
| 0 | -0.148890 | 0.913638 | -0.085523 | 0.895156 | 0.847046 | 0.278405 |
| 1 | -0.946445 | -0.198683 | 0.675028 | -0.736829 | -0.697327 | 0.151595 |
| 2 | 0.133159 | -0.908193 | -0.013260 | 0.907238 | 0.849707 | 0.340465 |
| 3 | 0.039357 | -0.043909 | -1.056483 | -0.791596 | -0.757792 | 0.296819 |
| 4 | 0.923868 | 0.261894 | 0.735958 | -0.676251 | -0.617502 | 0.553170 |

**Risk Ranking:**
1. Cluster 4: Highest risk
2. Cluster 2: Medium to high risk
3. Cluster 3: Moderate risk
4. Cluster 0: low to moderate risk
5. Cluster 1: Lowest risk


**Summary** 

The cluster banks and credit card companies should keep a close eye on cluster 4. Of the five clusters, cluster 4 has the highest risk of fraudulent transactions. This cluster is characterized by an extremely high failed transaction rate, a moderate transaction distance, and a high account balance.


