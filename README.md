# ML (Machine Learning): 
### Machine Learning is a branch of Artificial Intelligence (AI) that teaches computers to learn patterns from data and make predictions or decisions without being explicitly programmed for every task.

# Types of ML :
### Supervised learning
### Unsupervised learning
### Reinforcement learning
### Generative AI

# Supervised Learning: 
### A type of Machine Learning in which a computer learns from labelled data (data that already contains the correct answers).

#### In simple words: We teach the computer using examples where we already know the answers.

### Example:
#### - Input: Picture of a cat → Label: Cat
#### - Input: Picture of a dog → Label: Dog
#### The model learns from these examples and predicts labels for new pictures.

### Two main types:
#### 1. Regression – Predicts numerical values (e.g., house prices).
#### 2. Classification – Predicts categories (e.g., spam or not spam).


## Unsupervised Learning: 
### A type of Machine Learning in which a computer learns patterns and discovers hidden relationships from unlabelled data (data without predefined correct answers).

### In simple words: We give the computer data without answers, and it finds patterns or groups on its own.

### Example: Customer Segmentation
#### - Input: Customer shopping data.
#### - No predefined labels are given.
#### - The model groups customers based on similar shopping behaviour.

### Main types:
#### 1. Clustering: Groups similar data together (e.g., K-Means, DBSCAN).

## Remember:
### - Supervised Learning = Labelled Data.
### - Unsupervised Learning = Unlabelled Data.


## Reinforcement Learning (RL): 
### A type of Machine Learning in which an agent learns by interacting with an environment and receiving rewards or penalties for its actions.

### In simple words: The computer learns through trial and error. It tries different actions, learns from mistakes, and improves its decisions to get more rewards.

### Example: Teaching a robot to walk
#### 1. The robot tries to take a step.
#### 2. If it walks successfully, it receives a reward (+1).
#### 3. If it falls, it receives a penalty (-1).
#### 4. It learns from its experience.
#### 5. Eventually, it learns how to walk better.

### Four main components
#### 1. Agent: The learner (e.g., robot).
#### 2. Environment: Where the agent operates.
#### 3. Action: What the agent does.
#### 4. Reward: Feedback for its action.

### Real-life applications
#### - Self-driving cars.
#### - Robotics.
#### - Game-playing AI.
#### - Traffic signal optimization.
#### - Training intelligent agents.

## Remember the difference
### Type - Learning method
#### Supervised Learning - Labelled data
#### Unsupervised Learning - Unlabelled data
#### Reinforcement Learning - Rewards and penalties


## Foundational Supervised Learning Concepts
### Supervised Machine Learning is a type of machine learning in which a model learns from labelled data (data that already contains the correct answers) and uses that learning to make predictions on new, unseen data.

### There are five important concepts:
#### 1. Data
#### Data is the information provided to a machine learning model so it can learn patterns.

#### In supervised learning, data contains two main components:
#### - Features (X): Input information used to make predictions.
#### - Labels (Y): Correct answers or outputs associated with the inputs.
#### Example: Predicting house prices.
#### Size (sq. ft.) – Feature	House Price – Label
#### 1,000	₹30 lakh
#### 1,500	₹45 lakh
#### 2,000	₹60 lakh
#### 2,500	₹75 lakh

#### Here, house size is the feature, and house price is the label.
#### 2. Model
#### A model is a mathematical system or algorithm that learns patterns and relationships from the training data.

#### Example: A model learns that larger houses generally have higher prices.

#### Common supervised learning models:
#### - Linear Regression
#### - Decision Tree
#### - Random Forest
#### - Support Vector Machine (SVM)
#### - Logistic Regression
#### 3. Training
#### Training is the process of teaching a model using labelled data.

#### During training:
#### 1. The model receives input data.
#### 2. It makes predictions.
#### 3. Predictions are compared with actual answers.
#### 4. The model calculates the error (loss).
#### 5. It adjusts its parameters to reduce the error.
#### Example: The model predicts ₹50 lakh for a house whose actual price is ₹45 lakh. It learns from this error and adjusts its parameters.
### 4. Evaluating
#### Evaluation means checking how accurately the trained model performs on data it has not seen during training.

### Common evaluation metrics:
#### Problem type	Evaluation metrics
#### Regression	MAE, MSE, RMSE, R²
#### Classification	Accuracy, Precision, Recall, F1-score

#### Example: If a model correctly predicts 90 out of 100 house prices within a defined acceptable range, its performance can be assessed accordingly. For regression, we generally measure prediction errors rather than simple accuracy.
#### 5. Inference
#### Inference is the process of using a trained model to make predictions on new, unseen data.

#### Example:
#### - Input: House size = 1,800 sq. ft.
#### - Trained model processes the input.
#### - Output: Predicted price = ₹54 lakh.
#### The model is now being used, not trained.

#### Complete supervised learning workflow
#### 1. Data

#### Collect labelled data (Features + Labels)


#### 2. Model

#### Choose a machine learning algorithm


#### 3. Training

#### Learn patterns and reduce prediction errors


#### 4. Evaluating

#### Measure model performance on unseen data


#### 5. Inference

#### Make predictions using new data


### Quick revision
### Concept - Meaning
#### Data - Information used for learning
#### Model - Mathematical system that learns patterns
#### Training - Teaching the model using labelled data
#### Evaluating - Checking model performance
#### Inference - Making predictions using the trained model

## Remember: Training = Learning, Evaluation = Testing performance, Inference = Making predictions.


## Linear Regression

#### Linear Regression is a supervised machine learning algorithm and is a statistical technique used to find the relationship between variables. Input variables (features) and an output variable (target).

#### In simple words: Linear Regression finds the best-fit straight line through data points to predict future values.

## What is the Best-Fit Line?
#### The best-fit line is the line that minimizes the sum of squared differences between actual values and predicted values.

#### These differences are called residuals. Residual = Actual Value - Predicted Value

### 1. Real-world example
#### Suppose we want to predict a student's marks based on the number of hours they study.
#### Study hours (X)	Marks (Y)
#### 1	20
#### 2	30
#### 3	40
#### 4	50
#### 5	60

#### Here:
#### - Independent variable (X): Study hours.
#### - Dependent variable (Y): Marks.
#### - Goal: Predict marks based on study hours.

### Linear regression equation
#### In algebraic terms, the model would be defined as y = mx + b, where

 #### y is the value we want to predict.
 #### m is the slope of the line.
 #### x is input value.
 #### b is the y-intercept.

#### For example: y = 10 + 10x

#### If a student studies for 6 hours: y = 10 + 10(6) = 70


#### Types of Linear Regression
#### Type	Description
#### Simple Linear Regression	Uses one independent variable
#### Multiple Linear Regression	Uses two or more independent variables

#### Simple Linear Regression:y = mx + b

#### Example: Predicting salary using years of experience.

#### Multiple Linear Regression: y = m1x1 + m2x2 + m3x3 + m4x4 + m5x6 + b

import numpy as np
from sklearn.linear_model import LinearRegression

# Training data
X = np.array([[1], [2], [3], [4], [5]])
y = np.array([20, 30, 40, 50, 60])

# Create model
model = LinearRegression()

# Train model
model.fit(X, y)

# Predict marks for 6 study hours
prediction = model.predict([[6]])

print("Predicted Marks:", prediction[0])
print("Slope:", model.coef_[0])
print("Intercept:", model.intercept_)



## LOSS