![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML-green?logo=scikitlearn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)

# Sales Effectiveness – Lead Potential Prediction (PRCL-0019)

## 📌 Project Overview
Sales teams often manage a high volume of leads, but not all leads contribute equally to revenue. Inefficient lead prioritization can result in wasted effort and missed business opportunities.  
This project analyzes **sales effectiveness** and builds a **machine learning classification model** to predict whether a lead is **High Potential** or **Low Potential**, enabling better sales prioritization.

---

## 🎯 Project Objectives
- Perform exploratory data analysis (EDA) to understand sales effectiveness patterns
- Identify key factors influencing lead conversion
- Build and evaluate multiple machine learning models
- Select the most suitable model based on performance and business relevance
- Demonstrate an end-to-end, leakage-free ML pipeline

---

## 📊 Dataset Description
- **Source:** MySQL database  
- **Records:** 7,422  
- **Features:** 9  

### Key Attributes
- Lead creation timestamp  
- Product identifier  
- Lead source channel  
- Sales agent  
- Delivery mode  
- Lead status  

---

## 🧹 Data Cleaning & Preprocessing
- Verified and removed duplicate records
- Standardized column names for consistency
- Converted lead creation timestamps to datetime format
- Replaced invalid placeholder values in email fields
- Flagged invalid mobile numbers without dropping records
- Normalized categorical values to handle inconsistent text casing

---

## 🔍 Exploratory Data Analysis (EDA)
EDA was conducted to uncover sales effectiveness patterns:
- Distribution of lead statuses and conversion behavior
- Source-wise analysis of lead quality
- Delivery mode impact on lead outcomes
- Sales agent performance comparison
- Time-based lead generation trends  

Each visualization was accompanied by concise business insights.

---

## 🎯 Target Variable Definition
A binary target variable **Lead Category** was created using business logic:

- **High Potential:** Converted, Potential, In Progress Positive, Long Term  
- **Low Potential:** Junk Lead, Not Responding, Lost, In Progress Negative, Just Enquiry, Open  

This transformation simplified the prediction task while preserving business meaning.

---

## ⚙️ Feature Preparation
- Removed identifier fields such as email and mobile number
- Excluded raw datetime column to avoid unintended bias
- Applied one-hot encoding to categorical variables
- Removed status-related features to prevent target leakage
- Performed class imbalance check:
  - Low Potential ≈ 62%
  - High Potential ≈ 38%
- No resampling techniques were applied due to mild imbalance

---

## 🤖 Model Building & Evaluation
The dataset was split into training and testing sets using **stratified sampling**.  
The following models were trained and evaluated:

- Logistic Regression (baseline)
- Decision Tree
- Random Forest

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score  

Special emphasis was placed on identifying **High Potential** leads.

---

## 📈 Model Comparison & Selection
- Logistic Regression achieved higher accuracy but lower recall for High Potential leads
- Decision Tree improved recall but lacked stability
- **Random Forest provided the best balance between precision, recall, and F1-score**

✅ **Random Forest** was selected as the final model due to its balanced performance and business relevance.

---

## 💾 Model Persistence
The final trained Random Forest model was saved using **joblib**, enabling reuse and deployment without retraining.

---

## 🧪 Model Testing
A sample input was passed through the trained model to demonstrate prediction on unseen data.  
The model successfully classified lead potential and provided a confidence score, highlighting its real-world usability.

---

## 📊 Results & Business Impact
- Achieved realistic performance without data leakage
- Enables prioritization of high-value sales leads
- Improves sales efficiency and resource allocation
- Demonstrates an end-to-end, production-aware ML workflow

---

## 🔮 Future Improvements
- Engineer time-based features from lead creation timestamps
- Apply hyperparameter tuning to improve recall for High Potential leads
- Explore cost-sensitive learning for better business prioritization
- Integrate additional behavioral or follow-up data if available

---

## 🛠️ Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- MySQL
- Joblib

---

## 📁 Repository Structure
```
├── Sales_Effectiveness_PRCL_0019.ipynb   # Jupyter Notebook (EDA + ML pipeline)
├── lead_potential_model.pkl              # Trained Random Forest model
├── requirements.txt                      # Required Python libraries
├── .gitignore                            # Git ignore rules (env, cache files)
└── README.md                             # Project documentation
```

---

## 🔐 Security Note
Database credentials are managed using environment variables stored in a local `.env` file.  
Sensitive files are excluded from version control using `.gitignore`.

---

## 📌 Conclusion
This project demonstrates a complete, evaluation-safe machine learning pipeline for sales effectiveness analysis and lead potential prediction. The approach balances analytical rigor with practical business applicability and follows industry best practices.
---
### 📬 Contact Me

If you have any questions, suggestions, or feedback regarding this project, feel free to reach out through the channels below:

## 👤 Author

**Athuldev**  
Machine Learning | Data Science | Data Analytics

**📧 Email:** athuldevkoroth@gmail.com  
**🔗 GitHub:** https://github.com/athuldevkoroth  
**💼 LinkedIn:** https://www.linkedin.com/in/athuldev-k  

