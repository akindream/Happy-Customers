PROJECT: GkBBzHKeuuuJDE41

### **Customer Satisfaction Prediction for a Logistics Startup**  

#### **Background**  
A company, one of the fastest-growing startups in the logistics and delivery industry is striving to enhance customer satisfaction and optimize operations as they plan to expand globally. However, predicting customer dissatisfaction remains a challenge, especially when direct feedback is limited.  

To address this, a survey was conducted on a select customer cohort, gathering critical data on their experiences. The goal of this machine learning project is to analyze the dataset and build a predictive model that identifies key factors contributing to customer dissatisfaction. By **focusing on unhappy customers (target variable = 0)**, we can proactively improve their services.  

The dataset consists of **customer feedback attributes (X)** and a **target variable (Y)** that indicates customer satisfaction:  
- **Y (Target Variable):**  
  - **0** → Unhappy Customer  
  - **1** → Happy Customer  

- **Feature Descriptions:**  
  - **X1:** My order was delivered on time  
  - **X2:** Contents of my order were as I expected  
  - **X3:** I ordered everything I wanted to order  
  - **X4:** I paid a good price for my order  
  - **X5:** I am satisfied with my courier  
  - **X6:** The app makes ordering easy for me  

---

### **Data Processing & Strategy**  
- **Target Variable**: Binary classification (0 = Unhappy, 1 = Happy).  
- **Class Distribution**: No major class imbalance (69 happy vs. 57 unhappy customers).  
- **Preprocessing**:  
  - Cleaned and standardized the dataset.  
  - Performed feature scaling where necessary.  

- **Dimensionality Reduction via PCA**:  
  - The principal components explain variance as follows:  
    - **PC1: 37%**, **PC2: 19%**, **PC3: 15%**, **PC4: 12%**, **PC5: 10%**, **PC6: 8%**.  
  - These insights guided feature selection and model optimization.  

- **Recursive Feature Elimination (RFE) Ranking**:  
  - Features ranked from most to least significant using SGDClassifier: **X1, X4, X5, X2, X6, X3**.  
  - Using **NearestCentroid**, the following **recall(0) results** were observed:  
    - **All features included** → **58.3% recall(0)**  
    - **X1 alone** → **83% recall(0)** (highest single-feature performance)  
    - **Removing weakest features (X2, X6, X3)** → **Significant improvement in recall(0)**  

- **Key Insight**:  
  - The most important feature is **X1 (On-time Delivery)**, achieving **83% recall(0)**, the highest among all features.  
  - The weakest features **X2 (Order contents as expected), X6 (Ease of App Usage), and X3 (Ordered everything wanted)** can be removed to enhance the model’s predictive ability.  

---

### **Modeling Approach**  
- **Focus**: Prioritize identifying unhappy customers (Class 0) to implement targeted service improvements.  
- **Feature Selection**: Leveraged **PCA and RFE** for optimal input selection.  
- **Evaluation Metrics**:  
  - **Recall(0)** is the primary metric to ensure minimal false negatives for **unhappy customers**.  
  - **Other metrics**: Precision, F1-score, and accuracy for overall model assessment.  
- **Models Considered**:  
  - Initial model selection using **Lazy Predict**.  
  - **50 iterations** with different random seeds were used to determine the top-performing models.  
  - **NearestCentroid achieved 92% recall(0), making it the best model.**  
  - **Ensemble Voting Classifier (92%)** and **Stacking Classifier (83%)** were also tested.  
  - The **ensemble models combined NearestCentroid, Perceptron, and SGDClassifier** for better performance.  

#### **Final Model: NearestCentroid is the Best Model**  

---

### **Expected Impact**  
- **Proactively identify unhappy customers** and address their concerns.  
- **Optimize delivery operations** based on data-driven insights.  
- **Improve overall customer experience**, leading to increased retention and brand loyalty.  
- **Streamline questionnaires**, removing unnecessary questions while maintaining predictive accuracy.  

This machine learning project provides a structured approach to **predicting dissatisfaction**, allowing the company to take corrective measures and enhance customer satisfaction at scale. 🚀  

📞 **Read More on Medium:** [Predicting Customer Satisfaction: A Machine Learning Approach](https://medium.com/@akindream/predicting-customer-satisfaction-a-machine-learning-approach-for-a-growing-logistics-startup-89e6a685717d)  

💻 **GitHub Repository:** [Happy Customers](https://github.com/akindream/Happy-Customers)  

👉 **Connect on LinkedIn:** [Ernest Braimoh](www.linkedin.com/in/ernest-braimoh-29284b141)

💻 **YouTube:** [Ernest Braimoh](https://youtu.be/QGmoQVi82s4)
