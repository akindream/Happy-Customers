Customer Satisfaction Prediction for a Logistics Startup

Background

A company, one of the fastest-growing startups in the logistics and delivery industry, is striving to enhance customer satisfaction and optimize operations as they plan to expand globally. However, predicting customer dissatisfaction remains a challenge, especially when direct feedback is limited.

To address this, a survey was conducted on a select customer cohort, gathering critical data on their experiences. The goal of this machine learning project is to analyze the dataset and build a predictive model that identifies key factors contributing to customer dissatisfaction. By focusing on unhappy customers (target variable = 0), we can proactively improve their services.

The dataset consists of customer feedback attributes (X) and a target variable (Y) that indicates customer satisfaction:

Y (Target Variable):

0 → Unhappy Customer

1 → Happy Customer

Feature Descriptions:

X1: My order was delivered on time

X2: Contents of my order were as I expected

X3: I ordered everything I wanted to order

X4: I paid a good price for my order

X5: I am satisfied with my courier

X6: The app makes ordering easy for me

Data Processing & Strategy

Target Variable: Binary classification (0 = Unhappy, 1 = Happy).

Class Distribution: No major class imbalance (69 happy vs. 57 unhappy customers).

Preprocessing:

Cleaned and standardized the dataset.

Performed feature scaling where necessary.

Dimensionality Reduction via PCA:

The principal components explain variance as follows:

PC1: 37%, PC2: 19%, PC3: 15%, PC4: 12%, PC5: 10%, PC6: 8%.

These insights guided feature selection and model optimization.

Recursive Feature Elimination (RFE) Ranking:

Features ranked from most to least significant using SDGClassifier: X1, X4, X2, X5, X3, X6.

Using NearestCentroid, the following recall(0) results were observed:

All features included → 58.3% recall(0)

Removed weakest feature (X4) → 75% recall(0)

Further removals of features using the RFE ranking → 50%, 50%, 66.7%, 66.7% recall(0)

Confusion matrices confirm these results.

Key Insight:

The weakest feature in predicting unhappy customers is X6 (Ease of App Usage). Removing this feature improved recall(0) performance.

Modeling Approach

Focus: Prioritize identifying unhappy customers (Class 0) to implement targeted service improvements.

Feature Selection: Leveraged PCA and RFE for optimal input selection.

Evaluation Metrics:

recall(0) is the primary metric to ensure minimal false negatives for unhappy customers.

Other metrics: Precision, F1-score, and accuracy for overall model assessment.

Model Selection Process:

Used LazyPredict for initial benchmarking.

Selected top 11 models through 50 iterations with a fixed random seed.

Best Performing Models:

NearestCentroid → 92% recall (class 0), 92% accuracy

Ensemble Voting Classifier (NearestCentroid, Perceptron, SGDClassifier) → 92% accuracy

Stacking Classifier (NearestCentroid, Perceptron, SGDClassifier) → 83% accuracy

Hyperparameter tuning and cross-validation were applied to ensure optimal model performance.

Final Model: NearestCentroid is the Best Model

Expected Impact

Proactively identify unhappy customers and address their concerns.

Optimize delivery operations based on data-driven insights.

Improve overall customer experience, leading to increased retention and brand loyalty.

Streamline customer feedback questionnaires while maintaining prediction accuracy.

This machine learning project provides a structured approach to predicting dissatisfaction, allowing the company to take corrective measures and enhance customer satisfaction at scale. 🚀

Read More on Medium

For a detailed breakdown of the methodology, read the full article here: Predicting Customer Satisfaction – A Machine Learning Approach
https://medium.com/@akindream/predicting-customer-satisfaction-a-machine-learning-approach-for-a-growing-logistics-startup-89e6a685717d
linkedin: www.linkedin.com/in/ernest-braimoh-29284b141




