## RFM ANALYSIS USING PYTHON.

## INTRODUCTION.
You already know how important your customers are to your business. After all, you wouldn't be here without them. Still, many small companies fail to evaluate their customers to determine which ones are most crucial to their success.
You may measure your acquisition costs and segment customers based on behaviors they've taken on your site. However, this data doesn't tell you how purchasing behavior helps your business succeed. There are several ways to evaluate your clients, but one of the most effective and easily implemented is RFM analysis.

## QUESTION.
Read through this case study and solve it
https://statso.io/rfm-analysis-case-study/
PS:  RFM (recency, frequency, monetary) analysis is a marketing technique used to quantitatively rank and group customers based on the recency, frequency and monetary total of their recent transactions to identify the best customers and perform targeted marketing campaigns.

## SOLUTION.
The RFM model considers consumers' buying habits, including recency, frequency, and monetary values. It can help you identify your top customers to better advertise and market your products and services to them.

## Recency, Frequency, Monetary Value (RFM): Definition
RFM, also known as RFM analysis, is a type of customer segmentation and behavioral targeting used to help businesses rank and segment customers based on the recency, frequency, and monetary value of a transaction. RFM marketing can help marketers and small business owners determine their target audience to use their budget most effectively.

This method gives customers scores based on 3 factors:

## Recency:
Recency refers to how recent a customer's last purchase was. Customers who have made a recent purchase, typically within the last few weeks, still have the product and brand on their minds and are most likely to make a repeat purchase. You can measure recency however you deem necessary for your business. However, it's important to note that some companies might not have customers ordering every few days, weeks, or even months. For example, a car company might sell a single car to an individual within ten years.

## Frequency:
Frequency is how often the customer makes purchases, which can help you identify repeat customers. For example, many clients make frequent repeat purchases within a set timeframe. Frequency is essential in determining the individuals most likely to continue shopping with your brand after their first initial purchase.

## Monetary value:
Monetary value refers to how much a customer spends within a given period. It's always important to consider because it can tell you a few things about consumer behavior. For example, you might find that customers with the highest monetary value don't purchase items as frequently as others but typically buy the most expensive products when they do.

The values of each factor allow businesses to provide objective analysis and determine which audience to target for the most effective advertising and marketing campaigns.

## What's the purpose of RFM analysis?

RFM aims to help businesses identify their target audiences by telling them who the most valuable customers are to the company. With RFM analysis, you can determine what percentage of your customers support the business and leverage this information to develop more effective marketing campaigns while boosting brand loyalty and increasing conversions as customers move along the customer journey.

Predicting future customer behavior through RFM analysis can help businesses understand how likely customers will purchase another product or service and how much they will spend. But, of course, after further research, you may find that your company is supported by only a small percentage of its clients, and those are the individuals who should become your primary target audience.

## BENEFITS OF THE RFM MODEL.

Create successful campaigns. The RFM model can help you create more successful marketing campaigns to boost conversions. Because it tells businesses who their target audience should be based on recency, frequency, and monetary values. Knowing your target audience lets you spend your marketing dollars wisely because it means only advertising or marketing to those who are already interested in your products or services.

Retain at-risk clients. RFM analysis can help you effectively retain at-risk clients by understanding their purchasing behavior and how it impacts your business. It allows you to identify at-risk customers and take action at the right time to bring them back to your business.

Boost engagement. RFM can increase engagement and customer loyalty by allowing you to market to them with more personalized messages. In addition, RFM marketing enables you to create new opportunities to improve the relevancy of your messages based on past purchases and other buying behaviors.

Effectively use marketing resources. Every small business should aim to decrease its marketing spending while increasing its success. Unfortunately, they can only do that with the right data. RFM helps you identify your best customers, allowing you to segment them based on their rankings to create more effective and personalized marketing campaigns that reduce overall spending.

Performing RFM analysis and customer segmentation using Python requires data manipulation and analysis tools such as pandas and NumPy.
## Here's how I would do it:
## 1. I’ll start the task of RFM Analysis by importing the necessary Python libraries:


``` python
# Step 1: Import libraries.
import pandas as pd
from datetime import datetime
```
## I'll then load and inspect the dataset.

``` python
# Load the dataset 
data = pd.read_csv("rfm_data.csv")
print(data.head({
	'CustomerID': [8814, 2188, 4608, 2559, 9482, 8483, 8317, 6911, 8993, 3519, 9005, 9409, 5670, 8724, 9148, 5837, 2767, 2824, 9128, 1520, 8719, 8529, 8705, 6347, 4161, 2228, 6638, 5533, 9871, 9864, 1146, 9115, 5494, 4190, 5583, 2617, 6878, 5349, 5173, 8216, 4302, 5087, 2524, 2741, 2139, 5919, 7781, 9584, 2848, 1742, 3676, 9120, 3573, 2169, 4401, 8552, 4909, 9985, 7770],
	'PurchaseDate': ['11/04/2023', '11/04/2023', '11/04/2023', '11/04/2023', '11/04/2023', '11/04/2023', '11/04/2023', '11/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '12/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023', '13/04/2023'],
	'TransactionAmount': [943.31, 463.7, 80.28, 221.29, 739.56, 375.23, 272.56, 433.33, 16.55, 464.63, 120.75, 865.98, 392.7, 623.35, 99.15, 978.17, 299.57, 744.13, 388.9, 102.76, 338.56, 132.99, 751.53, 637.78, 692.36, 997.19, 417.64, 13.51, 849.53, 621.28, 585.27, 134.98, 974.55, 786.12, 693.38, 575.3, 226.63, 117.32, 711.7, 924.97, 793.2, 461.88, 922.06, 897.91, 664.65, 812.08, 566.9, 840.68, 811.38, 145.67, 223.31, 972.57, 110.25, 174.26, 192.99, 176.31, 252.03, 36.1, 195.71],
	'ProductInformation': ['Product C', 'Product A', 'Product A', 'Product A', 'Product A', 'Product C', 'Product B', 'Product C', 'Product D', 'Product C', 'Product C', 'Product A', 'Product B', 'Product C', 'Product D', 'Product D', 'Product B', 'Product D', 'Product B', 'Product B', 'Product B', 'Product A', 'Product D', 'Product C', 'Product B', 'Product C', 'Product B', 'Product B', 'Product C', 'Product C', 'Product B', 'Product C', 'Product D', 'Product D', 'Product D', 'Product A', 'Product B', 'Product A', 'Product C', 'Product D', 'Product D', 'Product B', 'Product C', 'Product D', 'Product D', 'Product C', 'Product A', 'Product B', 'Product A', 'Product D', 'Product C', 'Product B', 'Product D', 'Product C'],
	'OrderID': [890075, 176819, 340062, 239145, 194545, 691194, 826847, 963918, 112426, 139726, 972064, 597126, 995296, 739717, 629996, 387813, 342397, 334053, 281201, 629903, 313701, 562721, 466960, 614435, 859587, 777366, 812597, 768061, 750817, 761820, 821846, 205239, 831295, 745073, 564920, 789880, 343007, 462479, 645175, 309385, 430926, 838862, 834891, 247271, 183667, 123682, 877259, 957730, 744793, 943019, 599687, 923975, 299212, 723948, 785010, 961599],
	'Location': ['Tokyo', 'London
})
```

## 2. Calculating RFM Values
I’ll now calculate the Recency, Frequency, and Monetary values of the customers to move further:

``` python
# Convert the 'PurchaseDate' column to datetime objects
data['PurchaseDate'] = pd.to_datetime(data['PurchaseDate'], format='%d/%m/%Y')
# Have the following columns in your dataset:
# 'Count of CustomerID', 'Average of TransactionAmount', 'Max of OrderID', 'R', 'F', 'M'

# Define the RFM segments based on percentiles or custom thresholds
# You can choose different thresholds or percentiles based on your specific business goals.

# step 2: Define Recency (R) segments
data['RecencySegment'] = pd. cut(data['R'], bins=[-1, 1, 4, 9], labels=['High', 'Medium', 'Low'])

# Define Frequency (F) segments
data['FrequencySegment'] = pd. cut(data['F'], bins=[-1, 2, 5, 9], labels=['Low', 'Medium', 'High'])

# Define Monetary (M) segments
data['MonetarySegment'] = pd. cut(data['M'], bins=[-1, 3, 6, 9], labels=['Low', 'Medium', 'High'])
```
To calculate recency, we subtracted the purchase date from the current date and extracted the number of days using the datetime.now().date() function. It gives us the number of days since the customer’s last purchase, representing their recency value.


After that, we calculated the frequency for each customer. We grouped the data by ‘CustomerID’ and counted the number of unique ‘OrderID’ values to determine the number of purchases made by each customer. It gives us the frequency value, representing the total number of purchases made by each customer.

Finally, we calculated the monetary value for each customer. We grouped the data by ‘CustomerID’ and summed the ‘TransactionAmount’ values to calculate the total amount spent by each customer. It gives us the monetary value, representing the total monetary contribution of each customer.

## 3. Next, I'll define custom segments based on RFM scores.

``` python
# Step 3: Define custom segments based on RFM scores

def rfm_segment(row):
	if (row['R'] >= 7) and (row['F'] >= 5) and (row['M'] >= 4):
		return 'High-Value Customer'
	elif (row['R'] >= 7) and (row['F'] < 2) and (row['M'] >= 5):
		return 'At-Risk Customer'
	else:
		return 'Other'
# we are printing our data after using the highest valus of 'R': [7, 8, 9],
# print data.head({
    'Count of CustomerID': [23, 23, 20, 23, 21, 21, 21, 22, 27, 23, 21, 21, 24, 21, 23],
    'Average of TransactionAmount': [614.3891304, 513.596087, 433.395, 597.4004348, 487.2652381, 475.2161905, 463.6452381, 541.2472727, 471.1314815, 562.2530435, 523.1385714, 437.2114286, 481.4929167, 560.9342857, 441.5791304],
    'Max of OrderID': [957730, 966529, 968726, 945664, 982885, 936726, 972442, 960408, 985331, 924758, 991401, 979562, 946432, 994787, 966662],
    'R': [8, 8, 7, 8, 7, 7, 7, 8, 9, 8, 7, 7, 9, 7, 8],
    'F': [8, 5, 0, 8, 3, 3, 2, 6, 2, 7, 5, 1, 3, 6, 1],
    'M': [4, 4, 5, 3, 6, 3, 6, 4, 7, 2, 8, 6, 3, 9, 5]
})
data['Segment'] = data.apply(rfm_segment, axis=1)
```
Segment customers based on their RFM scores. You can use quartiles or percentiles to divide customers into segments. Common methods include:
Dividing customers into four or five segments (e.g., "Champions," "Loyal Customers," "At-Risk," "Lost Customers," etc.).
Using a combination of R, F, and M scores to create segment labels.


## 4. I'll then identify and label high-value customers, at-risk customers, and other segments.

``` python
# step 4: Analyze and develop customer segments
# You can analyze each segment to understand customer behavior and characteristics.

# Example: Identifying the "Best Customers" based on RFM segments
best_customers = data[(data['RecencySegment'] == 'High') & (data['FrequencySegment'] == 'High') & (data['MonetarySegment'] == 'High')]

# You can similarly identify other segments (e.g., at-risk customers, low-value customers) and develop strategies for each.

# Example: Identify at-risk customers
at_risk_customers = data[(data['RecencySegment'] == 'Low') & (data['FrequencySegment'] == 'Low') & (data['MonetarySegment'] == 'Low')]

# Example: Identify customer_distribution
customer_distribution = df.group by (["R", "F", "M"]).size().reset_index(name="Count")

# Analyze the Distribution of RFM Values within the Champions Segment
champions = df[df["R"] >= 7]
rfm_values_in_champions = champions[["R", "F", "M"]]

# Calculate the Correlation of RFM Scores within the Champions Segment
correlation = rfm_values_in_champions.corr()

# Number of Customers in All the Segments
segment_counts = {
    "Best Customers": len(best_customers),
    "At-Risk Customers": len(at_risk_customers),
    "Champions": len(champions),
}

# Compare RFM Scores of All the Segments
segment_scores = {
    "Best Customers": best_customers[["R", "F", "M"]],
    "At-Risk Customers": at_risk_customers[["R", "F", "M"]],
    "Champions": rfm_values_in_champions,
}

```
## 5. I'll then print the identified segments

``` python
# step 5: Print the identified segments
print("Best Customers:")
print(best_customers)
print("\nCustomer Distribution:")
print(customer_distribution)
print("\nDistribution of RFM Values within Champions:")
print(champions_rfm_values)
print("\nCorrelation of RFM Scores within Champions:")
print(correlation)
print("\nNumber of Customers in All the Segments:")
print(segment_counts)
print("\nCompare RFM Scores of All the Segments:")
print(segment_rfm_scores)

```
## 6. Implementation:

Implement the strategies and campaigns based on your analysis and segmentation.

## 7. Monitoring and Iteration:

Continuously monitor the effectiveness of your strategies and campaigns. Use feedback and data to adjust and refine your approaches.

## CONCLUSION

Using RFM as part of your marketing strategy can help you identify your top customers and find new ways to market to them based on their buying behaviors. Segmentation is crucial to improving engagement and increasing conversions for any business, regardless of size. With RFM, you can improve your marketing efforts throughout every stage of the customer journey and even personalize transactional emails to build loyalty.
