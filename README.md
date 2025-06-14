# Telecoms Customer Churn Analysis
### Project Overview:
The initiative examines 7,043 client records from a California-based telecom provider that offers phone and internet services. This project looks into a number of topics related to freshly joined accounts, churned customer accounts, and stayed customer accounts.  In order to assist the business in taking steps to make the accounts safely stayable, stayed accounts and newly joined accounts are divided into four classes: customers who joined at risk (Joined, @Risk), customers who stayed at risk (Stayed, @Risk), customers who stayed safe (Stayed, Safe), and customers who joined safely (Joined, Safe). In order to determine whether any high-value customer accounts are churned or at risk of churning, we are also classifying the customer accounts as high-value and low-value accounts based on a few important metrics.

### Dataset:
The dataset is from Maven Analytics challenge.


### Tools:
- Power Query
- Power BI

### Data Manupulation:

1. **Segmentation of High-valued and Low-valued Customer Accounts:** Three variables- Monthly Charge, Tenure and Referrals are considered as value metric in this case. The following steps are used:
	- Create a normalized value by spliting the allowance between the variables as 60% Monthly Charge, 20% Tenure and 10% Referrals.
	-  Customers below the average of the normalized value are considered as Low-valued customers and those above it are seen as High-valued customers.

   ![image](https://github.com/user-attachments/assets/85f7303e-a615-4a5f-b2d0-fe7c5df48f6e)
           Here, average value is 0.5116

2. **Segmentation of High Churn Risk and Low Churn Risk Accounts:** This is again calculated using the normalisation of a sum of variables. By looking at the negative deviations of different variables from the total churn rate of 28%, the variables are identified. The greater the negative value, the greater the likelihood that the variable contributes to churn risk. As a result, 16 variables are included in the total computation. These variables are: Contract, Married, Payment Method, Offer, Number of Refferrals, Device Protection Plan, Online Security, Online Backup, Premium Tech Support, Streaming Movies, Streaming TV, Streaming Music, Paperless Billing, Internet Service, Internet Type and Tenure in Months.
The metric used to segment the churn risk is the average value of the normalization of the total of these factors.  Customers who fall below the normalized value's average are categorized as having a high churn risk, while those who rise above it are classified as having a low churn risk.

   ![image](https://github.com/user-attachments/assets/18df07f0-e936-4084-b823-0caee518c38f)
        Here, average value is 0.4335

3. **Re-categorizing the Joined and Stayed client status:** Clients that have joined and stayed are categorized as "@Risk" if they are at high churn risk.  Classified as "Safe" otherwise.

   ![image](https://github.com/user-attachments/assets/1c588a8c-61af-4437-9c93-2829916a4682)

   ![image](https://github.com/user-attachments/assets/8834c161-f83e-401c-ab77-401a1147d5a9)


   
5. **Identifying Churn Risk Factors**: Combination of previously mentioned 16 variables and their values (using unpivot) helps to see which combination of each is most likely in churning customers.

  ![image](https://github.com/user-attachments/assets/d886310f-4ab6-46e6-9e8f-635e0e9adf2e)

### Dashboard:
![image](https://github.com/user-attachments/assets/edb798b1-a34b-4aab-a18a-ad2df96f64f0)




### Insights:
- Churned customers have higher average monthly charge than the stayed customers. 
- Significant number of high and low value accounts are churned.
- A lot of high-value stayed customers are at high risk of churning.
- Churned customers have common churning factors such as month to month contract, no online backup, paper billing, no online security, use of fiber optic internet, no premium tech support etc.
- Highest number of churned customers are from San Diego followed by Los Angeles.
- Most of the newly joined customers have low valued customer profile and most of them are at high churning risk.
- Only few customers joined safe and all of them have low value profile.

### Recommendations:
- Introduce exclusive or premium offerings for high-value customers.
- Monitor satisfaction and interaction levels of high spenders.
- Encourage customers to move to quaterly or yearly contract.
- Check issues with fiber optic internet.
- Introduce bundle offers for services such as online security, paperless billing, premium tech support etc.
- Check area specific issues, customer behaviour to reduce customer churning rate in different cities.

### References:
- [DG Analysis](https://dg-analysis.com/2022/08/06/telecoms-churn-maven-challenge/)
- [Maven Analytics](https://www.mavenanalytics.io/data-playground)
