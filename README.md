# FindDefault (Prediction of Credit Card fraud) - Capstone Project

## Problem Statement:
 A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash. It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

## About Credit Card Fraud Detection:
- **What is credit card fraud detection?**

  Credit card fraud detection is the collective term for the policies, tools, methodologies, and practices that credit card companies and financial institutions take to combat identity fraud and stop fraudulent transactions.  

  In recent years, as the amount of data has exploded and the number of payment card transactions has skyrocketed, credit fraud detection has become largely digitized and automated. Most modern solutions leverage artificial intelligence (AI) and machine learning (ML) to manage data analysis, predictive modeling, decision-making, fraud alerts and remediation activity that occur when individual instances of credit card fraud are detected.  

- **Anomaly detection**

  Anomaly detection is the process of analyzing massive amounts of data points from both internal and external sources to produce a framework of “normal” activity for each individual user and establish regular patterns in their activity.

  Data used to create the user profile includes:

  - Purchase history and other historical data
  - Location
  - Device ID
  - IP address
  - Payment amount
  - Transaction information

  When a transaction falls outside the scope of normal activity, the anomaly detection tool will then alert the card issuer and, in some cases, the user. Depending on the transaction details and risk score assigned to the action, these fraud detection systems may flag the purchase for review or put a hold on the transaction until the user verifies their activity.

- **What can be an anomaly?**
  - A sudden increase in spending
  - Purchase of a large ticket item
  - A series of rapid transactions
  - Multiple transactions with the same merchant
  - Transactions that originate in an unusual location or foreign country
  - Transactions that occur at unusual times

  If the anomaly detection tool leverages ML, the models can also be self-learning, meaning that they will constantly gather and analyze new data to update the existing model and provide a more precise scope of acceptable activity for the user.

 
## Project Introduction: 
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. 

In this Project, we have to build a classification model to predict whether a transaction is fraudulent or not. We will use various predictive models to see how accurate they are in detecting whether a transaction is a normal payment or a fraud. Let's start!

## Project Outline:
- **Exploratory Data Analysis:** Analysing and understanding the data to identify patterns, relationships, and trends in the data by using Descriptive Statistics and Visualizations.
- **Data Cleaning:** Checking for the data quality, handling the missing values and outliers in the data.
- **Dealing with Imbalanced data:** This data set is highly imbalanced. The data should be balanced using the appropriate Resampling Techniques (NearMiss Undersampling, SMOTETomek) before moving onto model building.
- **Feature Engineering:** Transforming the existing features for better performance of the ML Models. 
- **Model Training:** Splitting the data into train & test sets and use the train set to estimate the best model parameters.
- **Model Validation:** Evaluating the performance of the models on data that was not used during the training process. The goal is to estimate the model's ability to generalize to new, unseen data and to identify any issues with the model, such as overfitting.
- **Model Selection:** Choosing the most appropriate model that can be used for this project.
- **Model Deployment:** Model deployment is the process of making a trained machine learning model available for use in a production environment.

## Project Work Overview:
Our dataset exhibits significant class imbalance, with the majority of transactions being non-fraudulent (99.82%). This presents a challenge for predictive modeling, as algorithms may struggle to accurately detect fraudulent transactions amidst the overwhelming number of legitimate ones. To address this issue, we employed various techniques such as undersampling, oversampling, and synthetic data generation.
1. **Undersampling:** We utilized the NearMiss technique to balance the class distribution by reducing the number of instances of non-fraudulent transactions to match that of fraudulent transactions. This approach helped in mitigating the effects of class imbalance. Our attempt to address class imbalance using the NearMiss technique did not yield satisfactory results. Despite its intention to balance the class distribution, the model's performance was suboptimal. This could be attributed to the loss of valuable information due to the drastic reduction in the majority class instances, leading to a less representative dataset. As a result, the model may have struggled to capture the intricacies of the underlying patterns in the data, ultimately affecting its ability to accurately classify fraudulent transactions.
2. **Oversampling:** To further augment the minority class, we applied the SMOTETomek method with a sampling strategy of 0.75. This resulted in a more balanced dataset, enabling the models to better capture the underlying patterns in fraudulent transactions.
3. **Machine Learning Models:** After preprocessing and balancing the dataset, we trained several machine learning models, including:

   - Logistic Regression
   - K-Nearest Neighbors (KNN)
   - Random Forest Classifier
   - AdaBoost Classifier
   - XGBoost Classifier
4. **Evaluation Metrics:** We evaluated the performance of each model using various metrics such as accuracy, precision, recall, and F1-score. Additionally, we employed techniques like cross-validation and hyperparameter tuning to optimize the models' performance.
5. **Model Selection:** Among the various models and balancing methods experimented with, the XGBoost model stands out as the top performer when using oversampling techniques. Despite the inherent challenges posed by imbalanced datasets, the XGBoost algorithm demonstrates robustness and effectiveness in capturing the underlying patterns associated with fraudulent transactions. By generating synthetic instances of the minority class through oversampling methods like SMOTETomek, the XGBoost model achieves a more balanced representation of the data, enabling it to learn and generalize better to unseen instances. This superior performance underscores the importance of leveraging advanced ensemble techniques like XGBoost, particularly in the context of imbalanced datasets characteristic of credit card fraud detection.
   
In summary, our approach involved preprocessing the imbalanced dataset using undersampling and oversampling techniques, followed by training and evaluating multiple machine learning models. By systematically exploring different methodologies and algorithms, we aimed to develop robust fraud detection XGBoost model capable of accurately identifying fraudulent transactions while minimizing false positives.

## Future Work:
Anomaly detection techniques, including isolation forests and autoencoders, offer specialized capabilities for identifying outliers and anomalies within datasets. By incorporating these methods alongside traditional classification approaches, we can enhance the effectiveness of fraud detection systems. Isolation forests excel at isolating anomalies by randomly partitioning data points, making them particularly useful for detecting fraudulent transactions that deviate from normal patterns. Autoencoders, on the other hand, leverage neural networks to reconstruct input data, effectively learning representations of normal behavior and flagging deviations as potential anomalies.

Exploring the integration of advanced deep learning models like Convolutional Neural Networks (CNNs) and Recurrent Neural Networks (RNNs) alongside traditional machine learning techniques holds significant promise for enhancing fraud detection systems. These neural network architectures offer unique capabilities for processing sequential and structured data, which are crucial in identifying anomalous patterns indicative of fraudulent activities. By leveraging CNNs and RNNs, alongside hybrid models that combine the strengths of both deep learning and traditional algorithms, we can improve accuracy, adaptability, and overall performance in fraud detection. Additionally, techniques such as unsupervised learning, transfer learning, and feature extraction through deep learning can further enhance the efficiency and effectiveness of fraud detection systems. Through these advancements, we aim to bolster our ability to detect and prevent fraudulent transactions, ultimately safeguarding financial systems and protecting consumers from financial losses.

## Project Assets Overview:
- [data](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/tree/main/data):
  This folder contains the dataset(s) used in the project. Includes raw.csv file along with a README file explaining the dataset's attributes. The 'preprocessed_data.csv' and 'resampled_os.csv' data files have been excluded from the repository by adding them to the .gitignore file due to their large file sizes.
- [notebooks](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/tree/main/notebooks):
  This folder contains Jupyter notebooks consisting all the project work i.e. data exploration, preprocessing, feature engineering, model building, model training and evaluation for the best fitting model along with detailed explaination.
- [model](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/tree/main/model):
  This folder contains the trained machine learning model serialization files (e.g., Pickle files) used in the project. 
- [visuals](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/tree/main/visuals):
  This folder contains data visualizations and plots generated during exploratory data analysis or model evaluation.
- [Report](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/blob/main/Report.pdf):
  This is a documentation pdf file consisting the project report.
- [requirements.txt](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/blob/main/requirements.txt):
  This file contains all the required packages for this project. (Use command for installation: pip install -r requirements.txt)
- [app.py](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/blob/main/app.py):
  This app.py script essentially creates a web service(Flask application) that exposes a prediction endpoint, allowing user to send input data and receive predictions from the trained machine learning model. 

## Project Set-Up:
**Software And Tools Required for the Development of this Project:**
1. [VSCodeIDE](https://code.visualstudio.com/): Can also be require for evaluation
2. [GitCLI](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line)
3. [Github Account](https://github.com/)
4. [Heroku Account](https://www.heroku.com/)
5. [Postman](https://www.postman.com/) : Can also be require for evaluation

**Steps to Follow to Reproduce the Results:**
1. Open downloaded folder from the repository into VSCodeIDE.
2. Create New environment using commands-
   - conda install -p yourEnvname python==3.10
   - conda activate yourEnvname
3. Run following command to get all the required packages for this project-
   - pip install -r requirements.txt
4. Run all the jupyter notebooks (exclude training models, use model pickle files instead)from the 'notebooks' folder if want to reproduce the results of this project work. 
5. Run app.py file using command from terminal-
   - python app.py
6. Click on the link from the terminal as shown below-
   
   ![image1](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/40111259-c764-4d71-add9-bf2dedd4bed2)
   
   You will get ML API Web page as shown below -
   
   ![image2](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/5d55bf43-2e89-4f1f-aad7-5a639a398b4a)

   Fill the Values to Predict the Class of Transaction-
   
   ![image3](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/7d651f34-589d-4151-b0f2-9980789f51e1)

   Check the Prediction by clicking on the 'Predict' Button-
   
   ![image4](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/98fcfeec-7e54-470d-a6ec-abdf522dca77)
   
7. Same You can check with Postman Application-
   Open the Postman -> Click on + icon -> Paste the link followed by predict_api as shown below-

   ![postman1](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/d54933d7-73a4-4629-b890-74c6e2c8eb61)

   Click Body -> raw -> JSON

   ![postman2](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/a8e872b4-035e-40e3-a739-ffebbb43d93e)

   Change to Post method and add a data in the json format-

   ![postman3](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/27ae8694-e770-42a5-9d89-40784ce37b59)

   Click on the Send Button, You will get result as shown below-

   ![postman4](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/e8ba6df2-7488-446e-96a9-79749fb8fbb0)

8. Using Deployed model on Heroku Cloud Services-
   Check the details using following screenshots-
   
   ![deployed_model](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/782d630d-9e9d-4d74-bd3a-d008bc345c6b)

   ![model_deployed](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/a9f670c4-9b76-4c09-9a8e-b8b10cbda8b5)

   ![Heroku2](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/8b5fa01d-3ab5-47e3-84bd-8366418d80e2)

   ![Heroku3](https://github.com/SanamBodake/find-default-credit-card-fraud-detection-upgrad-capstone-project/assets/73472725/76bb3d43-9f5b-46b4-b508-dd33057530ec)

   

