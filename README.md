# Market Basket Analysis: Apriori vs FP-Growth

## Project Overview
This project implements and compares two association rule mining algorithms — Apriori and FP-Growth — using a dataset of customer product transactions. The goal is to extract association rules, identify patterns in customer purchasing behavior, and compare the results of both algorithms.

## Dataset
The dataset used for this analysis is the "Market_Basket_Optimisation.csv" which contains transactions made by customers. Each row represents a transaction, with product names as the columns. The dataset consists of 7501 transactions, each with up to 20 products.

## Methodology

### 1. Exploratory Data Analysis (EDA)
Before applying the algorithms, we explore the dataset to understand the most frequently purchased products and the distribution of transaction lengths. This helps in choosing appropriate parameters for the mining algorithms.

### 2. Data Preprocessing
The data is read from a CSV file stored in Google Drive. For Apriori, each row is converted into a clean list of items with all missing values removed. For FP-Growth, the data is additionally transformed into a one-hot encoded format using TransactionEncoder.

### 3. Apriori Algorithm
The Apriori algorithm is used to identify frequent itemsets and generate association rules. The following parameters were used:
- **Minimum support:** 0.003
- **Minimum confidence:** 0.2
- **Minimum lift:** 3
- **Maximum length:** 2

### 4. FP-Growth Algorithm
The FP-Growth algorithm is applied on the same dataset with the same parameters for a fair comparison. Unlike Apriori, FP-Growth builds a compact FP-tree structure to mine frequent itemsets more efficiently on larger datasets.

### 5. Results & Comparison
Both algorithms were evaluated using the same parameters. Apriori identified 9 association rules, while FP-Growth identified 12. All 9 Apriori rules were confirmed by FP-Growth, which additionally discovered 3 rules that Apriori missed. The strongest association in both cases was found between fromage blanc and honey, with a lift of 5.16.
