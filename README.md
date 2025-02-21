<h1>Predicting Customer Churn: Unlocking Insights for Retention at SyriaTel</h1>


<h2> Business Understanding</h2>
<h3>Introduction</h3>
<p>Customer churn is a key problem for telecommunications firms since losing customers has a direct influence on revenues and growth. This project seeks to create a machine learning classifier that can predict if a client will churn (leave SyriaTel). By studying customer usage habits, plan subscriptions, and contacts with the organization, we identify significant churn contributors and give practical ideas for reducing it.</p> <br>

<h2>Data Understanding</h2>
The collection has 3,333 entries, each representing a consumer. The idea is to evaluate these records for trends that suggest client turnover. Here's a full analysis of the data:

Target Variable

Churn: A binary variable that indicates if a client has churned. True: Customer churn occurred. False: The customer was kept.
Features: The number of features is 21 columns, including the target variable (churn).

Data Types:

1. `Categorical:`
  state, phone numbe, international plan, voice mail plan, churn.<br>
2. `Numerical:`
  Integer: account length, area code, amount of vmail messages, total day calls, total evening calls, total night calls, total international calls, and customer service calls.<br>
3. `Float:`
   total day minutes, total day charge, total evening minutes, total evening charge, total night minutes, total night charge, total international minutes, total international charge. <br>

<h2>Project Plan</h2>
1. Data Preparation
2. Model Creation
3. Model Selection
4. Recommendations

<h3>1. Data Preparation</h3>
<p>Lets get into it! Okay, we're attempting to figure out why consumers are leaving SyriaTel and who will churn in the near future. The dataset appears clean at first inspection, which is a good start; there are no missing values or duplicates.

Let's take a look at the goal variable, churn. I can already tell that the data is skewed. Only 14.5% ((483/3333)*100) of consumers have churned. That is not unusual in churn prediction, but it implies we cannot depend just on accuracy as a performance indicator. To ensure that the model correctly detects churners without biasing toward the majority class, we will need to consider accuracy, recall, and AUC-ROC values.

Another item on my radar is the state column. It contains too many distinct categories, thus it may not be very useful until we can aggregate it. And let's remove the phone number column it's merely an identifier with no predictive ability.

Once we've investigated and cleaned up the data, we'll need to address the class imbalance. Perhaps oversampling churners using SMOTE or modifying class weights in our model would do the job. Following that, we may experiment with several models—Logistic Regression for interpretability and something like Decision Tree.</p>

<h2>Model Creation</h2>
In this project I used 4 models:<br>
1. Logistic Regression Model
  ![Image](https://github.com/user-attachments/assets/f0de54bd-ea7a-4c1f-8158-20758274876a) 
  <br>
2. Logistic Regression Model with SMOTE
  
  <br>
3. KNN Model

  <br>
4. Decision Tree 
  
  <br>

<h2>Model Selection</h2>
![image](https://github.com/user-attachments/assets/e2e6e09a-40cf-4002-aabd-bc1c478b73cd)
The ROC curve clearly shows that the Decision Tree model outperforms the others. Its green curve is the steepest and spans the biggest area under the curve (AUC), indicating that it performs the best at differentiating between positive and negative classes. Essentially, the Decision Tree model finds a good mix between properly recognizing true positives and reducing false positives, making it the best option for this dataset.

<h2>Recommendations</h2>
1. <b>Check and Refine the Model:</b> 
<p>To guarantee that the model reacts to changing consumer behavior, regularly check its performance over time and retrain it with fresh data.  Consider including customer feedback and service interaction data to improve the model's predictive ability.</p> <br>

2. <b>Investigate Ensemble approaches:</b> 
<p>While the decision tree model worked well, more investigation into ensemble approaches such as Random Forest or Gradient Boosting might produce even better results.  These strategies may increase recall and general resilience, resulting in a more complete solution to the churn prediction problem.</p> <br>

3. <b>Customer Feedback Loop:</b>
<p>Create a feedback loop to collect data from clients who were expected to leave but opted to stay.  Use this information to improve retention techniques and the prediction model.</p> <br>

4. <b>Proactive Retention Strategies:</b>
<p>Create focused retention efforts for high-risk customers identified using the model. These might include targeted offers, better customer service, and loyalty programs.</p> <br>




