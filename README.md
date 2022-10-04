# Classification Project
## Heart Disease Predictor
Created By: Leah Nagy

### Table of Contents
1. [Presentation Slides](https://github.com/leahnagy/heart-disease-predictor/blob/main/slides.pdf)
2. [Project Code](https://github.com/leahnagy/heart-disease-predictor/blob/main/code.ipynb)
3. [Application Code](https://github.com/leahnagy/heart-disease-predictor/blob/main/streamlit_code.py)
4. [Heart Disease Predictor App](https://share.streamlit.io/leahnagy/streamlit-heart-disease/main/proj_streamlit2.py)

### Abstract
The goal of this project was to use classification models to predict the presence/history of heart disease or heart attack to help Functional Medicine health practitioners identify patients at risk of heart disease so they can create a prevention treatment plan for their patient. The data was provided by the CDC’s Behavioral Risk Factor Surveillance survey. After balancing the target variable classes, I was able to employ a Logistic Regression model and build an interactive app using StreamLit to predict the user’s probability of having heart disease.

### Design
While the original data comes from the CDC’s survey, this version of the data originates from [Kaggle](https://www.kaggle.com/datasets/alexteboul/heart-disease-health-indicators-dataset). The data has two classes – whether the survey respondent has heart disease or does not. This information will then be used to help healthcare practitioners identify patients that are at risk of heart disease to find ways to prevent any future disease or events. Often, a patient’s first symptom of heart disease is their last. With earlier detection and risk mitigation strategies, many lives will be saved.

### Data
The dataset contains 253,680 surveyed individuals with 21 features. Most of the features are questions related to lifestyle, such as alcohol consumption, smoking habits, exercise habits, etc. Other features include blood pressure, age, weight, and sex. The target variable has serious class imbalance with 91% of those surveyed as not having heart disease, while it was present in 9% of surveyed responses. 

### Algorithms
***Models***

The business use case for this project requires a probabilistic (soft) classification. I used a Random Forest model to compare the scores with the Logistic Regression model, and since it did not improve the scores and does not provide probabilistic predictions, the Logistic Regression model was chosen. 

***Class Imbalance***

Class weights, random over-sampling, SMOTE, and random under-sampling were used before settling on class weights to handle the class imbalance. All methods had similar F2 scores, however, the class weights model contains all the original samples without creating new samples, which could lead to overfitting. The class weights values were determined using cross-validation. 

***Model Evaluation and Selection***

The dataset was split using 80/20 train vs. holdout and the scores below were calculated using stratified 5-fold cross validation on the training portion only. The holdout set was used only to score the final model. 

The main metric used to evaluate the model was the F2 score. The purpose of this model is to help identify people at risk of heart disease and to create a plan to prevent it from occurring with the expectation of further studies to confirm the findings. Because of this, recall was weighted twice as heavily as precision to decrease the number of false negatives. 

**Final Logistic Regression 5-Fold CV Scores:** <br>
Accuracy Score: 0.694<br>
Recall Score: 0.794<br>
Precision Score: 0.207<br>
F2 Score: 0.506<br>
Brier Score: 0.694<br><br>

**Holdout:**<br>
Accuracy Score: 0.700<br>
Recall Score: 0.792<br>
Precision Score: 0.210<br>
F2 Score: 0.510<br>
Brier Score: 0.700<br>

### Tools
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling
- Matplotlib for plotting
- StreamLit for interactive app

### Communication
In addition to the presentation that included slides and visuals, the entire project will be posted on my blog on [GitHub](https://github.com/leahnagy) 

### Application
There's an app for that...[click here](https://share.streamlit.io/leahnagy/streamlit-heart-disease/main/proj_streamlit2.py)
