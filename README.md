# Capstone: Employee Review Monitoring

## Introduction

**The Great Resignation**, also known as the Big Quit, is an ongoing economic trend in which employees have voluntarily resigned from their jobs en masse, beginning in early 2021.

The COVID-19 pandemic has allowed workers to rethink their careers, work conditions, and long-term goals. As many workplaces attempted to bring their employees in-person, workers desired the freedom of remote work due to the COVID-19 pandemic as well as schedule flexibility, which was the primary reason to look for a new job of the majority of those studied by Bankrate in August 2021. Additionally, many workers, particularly in younger cohorts, are seeking to gain a better work–life balance. <sup>[source](https://en.wikipedia.org/wiki/Great_Resignation)</sup>

These trends highlight the importance for employers to adopt a data-driven approach to determining not just how many people are quitting, but who exactly has the highest turnover risk, why people are leaving, and what can be done to prevent it.

Employers should conduct a detailed data analysis to determine what's really causing their staff to leave. Which factors could be driving higher resignation rates? They could be factors such as compensation, work-life balance or training opportunites. This analysis can help identify trends and blind spots within the organization so as to retain employees through targeted intervention. <sup>[source](https://hbr.org/2021/09/who-is-driving-the-great-resignation)</sup>


## Problem Statement

In this period of the 'Great Resignation' / the 'Great Reshuffle', organizations should not just simply listen to the grievances of their employees and make empty promises, hoping that staffs would continue working day-by-day as if nothing is wrong. 

Employees have been growing more vocal year after year, and of course, during the pandemic, many of these workers may have simply reached a breaking point after months and months of high workloads, hiring freezes, and other pressures, causing them to rethink their work and life goals. Therefore, timely and targeted action needs to be taken by the firm before employees and ready to call it quits and say enough is enough.

Being a staff in our firm's data analytics and insights team, we were notified by our HR department that our employee retention rate has reached an all-time low this year and that the HR department do not have enough manpower to read through quarterly employee feedbacks made by all 10,000 employees in the firm. 

Hence, our team has been tasked with automating the process to identify positive and negative reviews made by staffs. Giving HR a brief overview on the ratio of positive to negative reviews and within these reviews, the firm is able to know what positive aspects had the firm done well and what pain points which are affecting retention rate. In doing so, department managers and HR could quickly gain actionable insights.

This would significantly lessen the workload of the HR staffs so that they are able to focus on improving other aspects of HR such as people welfare and organizational culture. 


## Executive Summary

This project explored data collected from Glassdoor reviews, which served as a basis for predicting sentiment of employee reviews within an organization. 

A few classification models were used in order to find our final production model for prediction. We have tested a number of combinations of vectorizers, classifiers and text normalization methods: 

**Text Normalization used:**

`Lemmatization`

**Vectorizers used:**

`CountVectorizer` and `Tfidfvectorizer`

**Machine Learning Models used:**

`Multinomial Naïve Bayes`, `Logistic Regression`, `SVM`

**Deep Learning Models used:**

`RNN-LSTM`

We found that a combination of Tfidf-vectorizer and Logistic Regression had the highest specificity score (75.4%) which was our primary scoring metric given that we would want a high specificity for negative reviews (i.e. number of correctly predicted negative reviews) since being able to accurately predict negative reviews would give the company insights into organizational problems.

Next, we would also want to ensure that actionable insights were easily obtainable by using a topic modeling algorithm known as `Latent Dirichlet Analysis`(LDA). From the LDA results ran on negative Glassdoor reviews, we were able to identify 5 topic groups, also known as pain points within the organization, such that HR / management could do further analysis om them and act on them as soon as they can to keep employee retention rates and employee satisfaction high. 

In conclusion, through this project, we hoped to save man-hours of HR staffs or managers that had to read through tens of thousands of lengthy reviews and manually decipher what actions needs to be taken as soon as possible. This is because losing talents within the organization could we very costly.


### Evaluation of models


Machine Learning model results:

![alt](/assets/ml_results.png)

RNN-LSTM model results:

![alt](/assets/dl_results.png)


Looking at the results above, Logistic Regression model with TFIDF-Vectorizer had performed the best overall. Hence, we will be choosing it as our production model for predicting sentiment of reviews from employees.


### Recommendations for further improvement

Areas for improvement:
- Try other estimators like KNN, XGBoost and RandomForest as well as other text normalization techniques such as Snowball or Lancaster Stemming.
- Further fine-tuning of RNN-LSTM model to improve training and validation scores.
- Try other deep learning models such as HuggingFace-BERT model using PyTorch.
- Using other pre-trained models from HuggingFace to predict sentiments of non-english reviews such as German and French.
- Deployment of models into an app that could upload quarterly reviews in csv format and gives an output to visualize the results for stakeholders.