# Market Basket Analysis with Apriori Algorithm

## Project Overview
This project implements the Apriori algorithm for market basket analysis using a dataset of product transactions. The goal is to extract association rules from the dataset and identify patterns in customer purchasing behavior. The project also includes exploratory data analysis (EDA) to better understand the dataset before mining.

## Dataset
The dataset used for this analysis is the "Market_Basket_Optimisation.csv" which contains transactions made by customers. Each row represents a transaction, with product names as the columns. The dataset consists of 7501 transactions, each with up to 20 products.

## Methodology

### 1. Exploratory Data Analysis (EDA)
Before applying the algorithm, we explore the dataset to understand the most frequently purchased products and the distribution of transaction lengths. This helps in choosing appropriate parameters for the Apriori algorithm.

### 2. Data Preprocessing
The data is read from a CSV file stored in Google Drive. Each row is converted into a clean list of items, with all missing (NaN) values removed before passing the transactions to the algorithm.

### 3. Apriori Algorithm
The Apriori algorithm is used to identify frequent itemsets and generate association rules. The following parameters were used:
- **Minimum support:** 0.003
- **Minimum confidence:** 0.2
- **Minimum lift:** 3
- **Maximum length:** 2

These parameters were chosen to focus on finding strong association rules between pairs of products.

### 4. Results
Association rules are generated from the frequent itemsets and sorted by lift value. The key metrics for evaluating each rule are:
- **Support:** How frequently the itemset appears in the dataset.
- **Confidence:** The probability that the second item is purchased when the first item is purchased.
- **Lift:** How much more likely the two items are to be bought together compared to being bought separately.

Using the parameters above, the algorithm identified a total of 9 association rules, with the strongest association found between fromage blanc and honey, achieving a lift of 5.16.
