
### **Author**: Heba Mohamed Abdelmonam Mahmoud 
### **Date**:  28-03-2023
### **email**: hebamohamed14101998@gmail.com
----
## **Problem Defination:**

Predict the outcome of a speed dating session between two individuals based on their profiles. The goal is to develop a recommendation system that can better match individuals in speed dating events. The dataset used for this task is clean and requires no extensive cleaning. The task is a binary classification problem where the model needs to predict whether the two individuals will have a successful match or not. By accurately predicting the outcome of speed dating sessions, the recommendation system can be improved to increase the chances of successful matches.

## **Input:**

The input is a dataset that includes a study by Columbia University explored gender differences in dating preferences.

#### **Dataset Description**:
Participants attended a dating event where they had a 4-minute date with every other participant of the opposite sex who attended the same event.
The participants decided to accept or reject their partner. If both the participant and partner matched, they received each other's contact information.
Participants rated their partners on six personal attributes: attractiveness, sincerity, intelligence, fun, ambition and shared interests.
Before and after the event, participants rated their preferences in the six attributes and gave themselves ratings.
Other information was collected about the participants' background and preferences.

## **Output:**
The main output is a numeric score representing predicted match potential.The scores are usually between 0 ( no match ) to 1 ( perfect match ). Higher scores mean a more promising, compatible match.

I will predict the test dataset using `predict_proba` to get the "match probability" between two individuals as evaluate using ROC/ AUC.

## **Required Data Mining Function:**

#### **Binary Classifier:**

  * LogisticRegression - LR
  * Support Vector Classification - SVC
  * RandomForestClassifier - RF
  * Multi-Layer Perceptron - MLP

#### **Model Fitting / Pipelining:**
* Pipeline
* GridSearchCV
* RandomizedSearchCV
* MakePipeline

#### **Evaluations**
* roc_curve
* auc

## **Challenges**
Some key challenges I see in this project are:

1. **Handling imbalanced classes**: Since successful matches are less frequent. This can bias models towards the majority class. *Oversampling*, undersampling, and class weights are techniques to help address imbalanced classes.

2. **Feature engineering**: Developing good features that capture compatibility and chemistry between individuals will be key.

3. **Model selection**: Choosing a model that can accurately learn the nuances of romantic compatibility will be important. Options could include logistic regression, random forests, neural networks, and support vector classifier.

4. **Generization**: The recommendations should ideally be personalized for each new query (dating pair). This means the model would need to generalize well beyond just the training data distributions. Ensemble methods (Random forest and xg boost) or neural networks could help here.

## **Impact**
The impact of this project can be significant in the field of dating and matchmaking. By accurately predicting the outcome of speed dating sessions, the recommendation system can be improved to increase the chances of successful matches. This can help people to find compatible partners more easily and increase their likelihood of forming lasting relationships.

The project can also have wider applications in other fields such as e-commerce, healthcare, and finance, where predictive modeling can be used to make better decisions and improve customer satisfaction. 

## **Ideal Solution:**

- Using Bayesain search is a good choice as it is able to explore a wide range of hyperparameters in an efficient manner, without requiring too much computational power or time.
- Using XGBoost with this dataset is the best model as it achieved the highest score in terms of AUC and was able to generalize well on the test set. Additionally, XGBoost has several advantages over other machine learning algorithms, such as built-in regularization techniques, handling of missing values, speed, and flexibility. 


## **Methodology:**

 **Load the dataset.**

 **Data exploration and Preprocessing**: data exploration and preprocessing, which involves cleaning and transforming the data into a suitable format for machine learning algorithms.

 **Feature Selection**:Extract features from the profiles that could be indicative of match likelihood (common interests, personality traits, etc. Ai the end of this step I created 3 versions from the orginal dataset:

  1. A Dataset after dropping nulls features.
  2. A Dataset after dropping nulls features + highly correlated Features.
  3. A Dataset after dropping nulls features + Oversampling.


 **Build Pipline.**

 **Apply complete Pipline**: from data preprocessing to model training as a single pipeline: 
  
  - **Grid search trial**.
    * LogisticRegression - LR.
    * Support Vector Classification - SVC.
    * RandomForestClassifier - RF.
    * Multi-Layer Perceptron - MLP.

  - **Random search trial.**
    * LogisticRegression - LR.
    * Support Vector Classification - SVC.
    * RandomForestClassifier - RF.
    * Multi-Layer Perceptron - MLP.
    * XGBoost - XGB.

  - **Bayesian search trial.**
    * LogisticRegression - LR
    * Support Vector Classification - SVC
    * XGBoost - XGB.

    
 **Evaluate the model's performance**

 **Predict test dataset:** Use the trained model to predict match likelihood for new pairs of profiles.