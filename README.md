# Market Basket Optimization with Apriori Algorithm

## Project Overview
This project implements the Apriori algorithm for market basket optimization using a dataset of product transactions. The goal is to extract association rules from the dataset and analyze patterns in customer purchasing behavior.

## Dataset
The dataset used for this analysis is the "Market_Basket_Optimisation.csv" which contains transactions made by customers. Each row represents a transaction, with product names as the columns. Some transactions may contain empty (NaN) values where customers did not purchase products.

### Data Structure
The dataset consists of 7501 transactions, each with up to 20 products. The data is structured with each product purchase in a separate column.

## Methodology

1. **Data Preparation**: 
   - The data is read from a CSV file stored in Google Drive.
   - Missing values are handled by ignoring them during the rule generation process.

2. **Apriori Algorithm**: 
   - The Apriori algorithm is used to identify frequent itemsets in the dataset.
   - The algorithm's parameters:
     - Minimum support = 0.003
     - Minimum confidence = 0.2
     - Minimum lift = 3
     - Maximum length = 2
   - These parameters were chosen to focus on finding strong association rules between pairs of products.

3. **Association Rules**: 
   - Association rules are generated from the frequent itemsets, showing how likely the presence of one product is to be associated with another.
   - Key metrics for each rule:
     - **Support**: How frequently the itemset appears in the dataset.
     - **Confidence**: The probability that the second item is purchased when the first item is purchased.
     - **Lift**: A measure of how much more likely the two items are to be bought together than separately.

4. **Results**:
   - The top rules are presented based on the lift value, which indicates the strength of the association between the two products.
   
