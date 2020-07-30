# CLUSTERING OF CREDIT CARD CUSTOMERS
Author: Kevin Lee<br />Email: kvnlee97@gmail.com<br />Data Source: [Kaggle](https://www.kaggle.com/arjunbhasin2013/ccdata)
## 1 - DEFINING THE PROBLEM
### THE PROBLEM
A bank has collected data on the usage behavior of their credit card holders over the last six months. The bank's marketing team wants to set up a marketing campaign by dividing these customers into groups in order to better target their needs.<br />
### THE GOAL
The marketing team is looking for distinctive groups within the customer data in order to target product advertisements based on the usage behavior of the customer groups.<br />
## 2 - DISCOVERING THE DATA
### 2.1 - DATA DICTIONARY
CUST_ID: Identification of Credit Card holder<br />
BALANCE: Balance amount left in their account to make purchases<br />
BALANCE_FREQUENCY: How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)<br />
PURCHASES: Amount of purchases made from account<br />
ONEOFF_PURCHASES: Maximum purchase amount done in one-go<br />
INSTALLMENTS_PURCHASES: Amount of purchase done in installment<br />
CASH_ADVANCE: Cash in advance given by the user<br />
PURCHASES_FREQUENCY: How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)<br />
ONEOFF_PURCHASES_FREQUENCY: How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)<br />
PURCHASES_INSTALLMENTS_FREQUENCY: How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)<br />
CASH_ADVANCE_FREQUENCY: How frequently the cash in advance being paid<br />
CASH_ADVANCE_TRX: Number of Transactions made with "Cash in Advanced"<br />
PURCHASES_TRX: Numbe of purchase transactions made<br />
CREDIT_LIMIT: Limit of Credit Card for user<br />
PAYMENTS: Amount of Payment done by user<br />
MINIMUM_PAYMENTS: Minimum amount of payments made by user<br />
PRCFULL_PAYMENT: Percent of full payment paid by user<br />
TENURE: Tenure of credit card service for user<br />
### 2.2 - CLEANING UP THE DATA
The CUST_ID column doesn't contribute to the analysis process, so it is dropped. The data is then normalized through the use of StandardScaler from sci-kit learn.<br />
### 2.3 - LOOKING AT THE DISTRIBUTION OF THE DATA
![Mean Histogram](/images/1.png)<br />
### 2.4 - CORRELATION HEATMAP
![Mean Correlation](/images/2.png)<br />
### 2.5 - POINTS OF INTEREST
- There appears to be two groups of customers on the PURCHASES_FREQUENCY histogram:
  * Cardholders that make purchases frequently
  * Cardholders that rarely use their card for purchases
- Most customers do not pay their balance in full
- Most customers have been with the bank for over 10 years
### 2.6 - K-MEANS CLUSTERING
![Mean Elbow Method](/images/3.png)<br />
Using the elbow method, it's a little bit unclear where an elbow exactly forms. The curve does start dip and diminish around the 8th cluster so I went ahead and used eight clusters for the test.<br />
### 2.7 - THE CLUSTERS
![1](/images/4.png)<br />
![2](/images/5.png)<br />
![3](/images/6.png)<br />
![4](/images/7.png)<br />
![5](/images/8.png)<br />
![6](/images/9.png)<br />
![7](/images/10.png)<br />
![8](/images/11.png)<br />
![9](/images/12.png)<br />
![10](/images/13.png)<br />
![11](/images/14.png)<br />
![12](/images/15.png)<br />
![13](/images/16.png)<br />
![14](/images/17.png)<br />
![15](/images/18.png)<br />
![16](/images/19.png)<br />
![17](/images/20.png)<br />
### CLUSTER TAKEAWAYS
#### CLUSTER 0
- The cardholders in this cluster are varied in purchase frequency
- Most purchases are small purchases
- Generally do not do any cash advances
#### CLUSTER 1
- Unlike cluster 0, cluster 1 cardholders are more frequently making purchases
  * These purchases are for larger dollar amounts
  * Cluster 1 cardholders also do more one-off purchases, where as cluster 0 cardholders generally did not do any
#### CLUSTER 2
- Cluster 2 cardholders are frequently updating their balance, while generally keeping purchase frequency low
  * Cluster 2 cardholders probably make infrequent purchases and pay it off right away  
#### CLUSTER 3
- Cluster 3 cardholders make the largest purchases out of all the clusters
  * This customer makes both one-off purchases as well as installment purchases with frequency
#### CLUSTER 4
- Cluster 4 cardholders are the most frequent cash advance takers
- They have the largest credit card balances of the eight clusters
#### CLUSTER 5
- Cluster 5 cardholders are very similar to cluster 3 cardholders:
  * They make large purchases as well as one-off purchases
  * Unlike cluster 3 cardholders, cluster 5 cardholders do not make installment purchases as often.
#### CLUSTER 6
- Cluster 6 cardholders make the largest one-off and installment purchases
  * Customers that could potentially use a loan or a line of credit
#### CLUSTER 7
- Cluster 7 cardholders mostly make installment purchases
  * Another set of customers that could be targeted with loan or line or credit offers
