# Market Basket Analysis: Apriori vs FP-Growth

## Project Overview

This project applies and compares two popular association rule mining algorithms — **Apriori** and **FP-Growth** — on a retail transaction dataset.

The goal is to:
- Discover frequent item combinations
- Extract meaningful association rules
- Analyze customer purchasing behavior
- Compare the performance and results of both algorithms
- Build a simple recommendation system based on discovered patterns

## Dataset

The dataset used is **Market_Basket_Optimisation.csv**, which contains real-world-like grocery transactions, where each row represents a customer's basket.

## Methodology

### 1. Exploratory Data Analysis (EDA)

Before applying any algorithm, exploratory analysis was performed to:
- Identify most frequently purchased items
- Analyze transaction length distribution
- Understand purchasing patterns

### 2. Data Preprocessing

Two preprocessing approaches were used:

- **Apriori**: Transactions converted into lists of items
- **FP-Growth**: One-hot encoding using `TransactionEncoder`

### 3. Apriori Algorithm

The Apriori algorithm was applied to generate frequent itemsets and association rules.

**Parameters used:**
- Minimum support: 0.003  
- Minimum confidence: 0.2  
- Minimum lift: 3  
- Maximum itemset length: 2  

### 4. FP-Growth Algorithm

FP-Growth was applied using the same parameters for fair comparison.

Unlike Apriori, FP-Growth:
- Builds a compressed FP-tree structure, requires fewer database scans and performs better on larger datasets

### 5. Network Visualization

A directed network graph was created to visually represent association rules:
- Nodes represent products
- Edges represent rules
- Edge thickness and color represent rule strength (lift)

This helps in identifying strong product relationships visually.

### 6. Recommendation System

A simple rule-based recommendation system was implemented:

- Input: product name
- Output: associated products based on strongest rules
- Includes fallback handling for products with no rules

This simulates a basic E-commerce recommendation engine.

## Results & Comparison

Both algorithms were evaluated under identical parameters.

| Algorithm   | Rules Found |
|-------------|------------|
| Apriori     | 9 rules    |
| FP-Growth   | 12 rules   |

### Key Findings:
- All Apriori rules were also discovered by FP-Growth
- FP-Growth identified additional associations not captured by Apriori
- Strongest rule found:
  - **fromage blanc → honey**
  - Lift: **5.16**

## Conclusion

This project demonstrates how association rule mining can uncover hidden relationships in transactional data. FP-Growth proved to be slightly more effective in discovering additional rules, while both algorithms produced consistent core insights.
