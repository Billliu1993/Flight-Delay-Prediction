# Flight-Delay-Prediction

## Code deployment
<br/>
The codes were written in python, and the notebook was uploaded to this repo. Due to the large size of data, the Flight Delay dataset was not included. To successfully deploy the codes, the essential packages (latest versions) listed at the beginning of the notebook should be installed. The data file could be directly downloaded at "Data Scientist – Flight Delay Prediction" at hackmd @terminal 1 "Technical Assessment", and should be saved to the same folder as the python notebook.
<br/>

## Project overview
<br/>
The goal of this project is to predict the claimed amount (between 0 and $800) assigned to fights caused by delay. To solve this problem, I first converted it into a binary classification problem, where the delay time > 3 (including "cancelled") is labeled as 1, otherwise labeled as 0. Then, the binary classification models were constructed with engineered features based on exploratory data analyst (EDA) results, then the predicted claimed amount was determined as predicted claimed amount = $800 * probability(label = 1). 
<br/>

## Project details
<br/>
A high-level summary of the procedures to solve this problem could be found at the presentation slides uploaded to this repo. The entire work could be divided into 3 sections:
<br/>

1. EDA
To generate idea on how the features should be engineered for modeling, EDA was first conducted using Tableau. Particularly, I investigated into what factors correlated with delay outcomes, and identified the features from 3 domains: time domain (including week of the year, day of the week, and hour of the day), location domain (including arrival airport groups based on the average delay, and the distance bwteen departure and arrival airports), and airline domain (including airline groups based upon the average delay). The features were created accordingly in python, and carried to the modeling step.
<br/>

2. Modeling
With features created and processed, the machine-learning models were created, trained, compared, and tuned using AUC-ROC as the primary evaluation matric. One major challenge  in modeling was that the prediction label distribution was heavily imbalanced, with label = 1 as the minority group. Therefore, the Synthetic Minority Over-sampling TEchnique (SMOTE) technique was used to oversample the minority class (label = 1). This approach significantly improve the modeling performance on such imbalanced dataset.
<br/>

3. Result Analysis

<br/>

## Outcome highlights
<br/>

<br/>

## Future work
<br/>
In my opinion, there are three main areas where this work could be improved:
<br/>
1. Explore different grouping of airlines and arrival airports. In the work, the grouping of airlines and arrival airports was based upon the average delay with threshold determined manually. If time allows, I could also conduct more detailed statistical analysis to explore other thresholds for grouping.
<br/>
2. Explore flight number. Flight number might also correlate with the delay outcomes. However, due to the large number of unique flight numbers present in the dataset, flight numbers could not be directly used for modeling, and the segmentation of the flight numbers would be needed.
<br/>
3. Further tune the model hyperparameters. The model performance could be potentially further improved by continuing the hyperparameters. Specifically, in this work, I first compare different model with default hyperparameters, and then, further tune the parameters of the best-performing model. If time allows, I could do more detailed grind search to identify a better set of hyperparameters.
<br/>
