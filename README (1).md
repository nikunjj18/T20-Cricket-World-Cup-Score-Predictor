**Cricket Score Predictor – Machine Learning Project**

This project predicts the final score of a cricket innings using machine learning.
It is built using Python, Scikit-Learn, XGBoost, and Streamlit for deployment.

📁**Project Structure**

ML_project/
│── Cricket Score.ipynb                # Jupyter Notebook with all training code
│── README(1).md   
│── best.py                  # Streamlit web application
│── dataset_t20.pkl           # Dataset (CSV)
│── pipelining            # Saved final ML pipeline
│── requirements.txt 


**1. Project Overview**

The goal of this project is to build a regression model that predicts final runs scored based on match conditions such as:

Batting team
Bowling team
Current score
Balls bowled
Wickets left
Runs in last 3 overs
Current run rate
City


**📊 2. Dataset Description**

| Feature           | Description                |
| ----------------- | -------------------------- |
| batting_team      | Team currently batting     |
| bowling_team      | Team bowling               |
| current_score     | Score at prediction moment |
| balls_bowled      | Total balls bowled so far  |
| wickets_left      | Wickets remaining          |
| runs_last_3_overs | Form indicator             |
| crr               | Current Run Rate           |
| city              | Match location             |
| final_score       | Target variable            |

https://www.kaggle.com/veeralakrishna/cricsheet-a-retrosheet-for-cricket?select=t20s
Link to access datasets taken for this project. To open dataset, Click on the link mentioned. There we can find multiple sections of cricket matches such as ipl, bbl, ODIs,Tests, T20s etc. Among these, click on T20s to see the project dataset.

**3. Machine Learning Workflow**

**Data Cleaning**
1.Missing value handling
2.Type conversions

**Feature Engineering**
1.One-Hot Encoding for categorical columns
2.Scaling numeric columns

 Algorithm Testing

**Models tested:**

**Model	Status**

| Model                | Status            |
| -------------------- | ----------------- |
| Linear Regression    |  High error      |
| Decision Tree        |   Good        |
| Random Forest        |  Good            |
| AdaBoost             | Strong       |
| XGBoost              |  Weak   
|Ridge/Lasso                High error      
KnearestNeighbours         High variance    
| **Voting Regressor** | **Best Model** |


**🏆 4. Best Model: VOTING REGRESSOR**

The final model is an ensemble of two strong regressors:
decision tree+ AdaBoost 


📌 Voting Regressor gave the lowest error and best generalization, making it the final choice.


**🧪 5. Final Machine Learning Pipeline**

The final pipeline includes:

StandardScaler → scale numeric features
OrdinalEncoder → convert teams/city to vectors
VotingRegressor → final model

** 6. Screenshot of deployed model**





<img width="793" height="571" alt="image" src="https://github.com/user-attachments/assets/999f5b6e-3756-4d50-9806-59c139226b94" />






<img width="737" height="560" alt="image" src="https://github.com/user-attachments/assets/fa94d54a-bd20-442a-a369-321ed98b3efc" />






** 7. Dependencies**

Python ≥ 3.8, 
pandas, 
numpy, 
scikit-learn, 
xgboost, 
streamlit, 
joblib (for saving/loading pipeline)


**8. Expected Outputs**

1. Jupyter Notebook:
Data preprocessing results
Model training and evaluation metrics (MAE, RMSE, R²)
Comparison of multiple models

2. Streamlit App:
User inputs match conditions: batting team, bowling team, current score, balls bowled, wickets left, last 3 overs runs, crr, city
Displays predicted final score instantly

3. Model Performance (Voting Regressor):
   Model used in voting regressor -DecisionTreeRegressor and ADABoost regressor
MAE(test): 4.683177874327976
R² (Test): 0.9560710665919709
RMSE 8.348266971477013
Standard error of estimate : 8.360672559554418
Model is balanced
MAE(train): 4.229465465629779
 MAE(test): 4.683177874327976



