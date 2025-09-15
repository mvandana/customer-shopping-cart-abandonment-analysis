**🛒 Customer Shopping Cart Abandonment Analysis**

**Summary**

Retailers often watch customers browse, add items to their cart, and then leave without buying. This project focuses on predicting when that happens. Using session data, I built a classification model that flags which sessions are most likely to end in cart abandonment. The goal is to help businesses catch these users in time and offer the right nudge to complete the sale.

**The Impact**

Why it matters-

Cart abandonment directly affects revenue. If we can spot users who are about to leave before buying, we can act, maybe with a discount, free shipping, or a reminder email. That simple step could mean the difference between a lost opportunity and a conversion.

What I did-

•	Identified the five most important behaviors that lead to abandonment
•	Trained a logistic regression model using only those signals
•	Built and saved a deployable model that’s ready to plug into a scoring system

**My Approach**

1. Data Cleaning and Transformation
	•	Parsed 13 session-level attributes like page views, cart activity, and login status
	•	Fixed missing values using averages where needed
	•	Converted categorical values into usable numeric format

2. Exploratory Data Analysis
	•	Plotted distributions and trends to understand how users behave during sessions
	•	Used boxplots and heatmaps to detect outliers and strong correlations
	•	Noticed that users who never view product details often abandon the cart

3. Feature Engineering
	•	Normalized numerical features with Min-Max Scaling
	•	Applied Box-Cox transformations to reduce skew and manage outliers
	•	Combined clean numerical and categorical data into a final dataset

4. Feature Selection
	•	Used Recursive Feature Elimination (RFE) and Random Forest to rank feature importance
	•	Final predictors included:
	•	Number of items added to cart
	•	Number of checkout confirmations
	•	Checkout initiations
	•	Login activity
	•	Page views

5. Modeling and Oversampling
	•	Used SMOTE to handle class imbalance and create a balanced training set
	•	Trained a logistic regression model on selected features
	•	Split the data into train and test sets for validation

6. Evaluation and Diagnostics
	•	Measured performance
	•	Verified predictions with confusion matrices
	•	Saved the model using pickle for reuse

**Business Value**

This model helps teams identify at-risk sessions before they’re lost. It makes it possible to act while the user is still on the site, not after they’ve gone. Companies can use this to:
	•	Show a discount popup at the right moment
	•	Trigger follow-up emails based on session risk
	•	Optimize page flows for high-risk user paths
