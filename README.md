# BigMart Sales Prediction
# Project Overview
This project aims to predict the sales of different products across BigMart outlets using historical sales data. By understanding key factors influencing sales, BigMart can make data-driven decisions to optimize product placement and store performance.

# Dataset
The dataset consists of sales records for 1559 products across 10 stores, with attributes like product weight, visibility, price, store type, and location.

# Key Variables:
Item_Identifier: Unique product ID

Item_Weight: Weight of the product

Item_Fat_Content: Low fat or regular fat classification

Item_Visibility: Percentage of store display area allocated to the product

Item_Type: Product category

Item_MRP: Maximum retail price

Outlet_Identifier: Unique store ID

Outlet_Establishment_Year: Store opening year

Outlet_Size: Store size (Small, Medium, Large)

Outlet_Location_Type: Store’s city tier (Tier 1, Tier 2, Tier 3)

Outlet_Type: Type of store (Grocery store vs. Supermarket)

Item_Outlet_Sales: Target variable (sales of the product at the store)

# Approach Taken
## •	Exploratory Data Analysis (EDA): I conducted EDA to identify patterns and correlations across different variables. 
## Key insights included:
o	Item MRP has a strong impact on sales (higher-priced items generally sell more).

o	Outlet Type influences sales, with supermarkets performing better than grocery stores.

o	Found Item Visibility has some zero values (unrealistic).

## •	Handling Missing Values: Some stores did not report all the data, leading to missing values. I imputed missing Item_Weight values using the average weight for similar products and handled Outlet_Size by using Mode across different Outlet Type.
## •	Feature Engineering: Created new features such as Store Age (calculated from Outlet_Establishment_Year) and standardized Item Fat into Low Fat and Regular categories for better generalization.
# Model Building & Optimization
I initially trained a Random Forest Regressor, which performed well, but I further improved the accuracy by also using an XGBoost Regressor.
•	Hyperparameter Tuning: Used GridSearchCV to find the best combination of hyperparameters.

•	Segmentation-Based Models: Instead of a single model, I built multiple models based on Outlet Location Type (Tier 1, Tier 2, Tier 3), Item Fat Content, and Outlet Type to capture variations in sales patterns across different categories.
# Next Steps
1.	Refine Feature: Analyze features interaction to understand combination of feature that could help us in improving the performance of the Model.
2.	Address Item Visibility Issues: Since some products have 0 visibility, adjust them based on the average visibility for similar items.
3.	Advanced Model Stacking: Combine predictions from multiple models (e.g., Random Forest + XGBoost) to further boost accuracy.
This structured approach ensures better sales predictions and provides actionable insights for BigMart to optimize product placement and store strategies. 
