# GA_Project_3_Subreddit_Classifier
## Webscrapping Reddit Threads
## Yanda DSI 33
 Classification model on CatAdvice and DogAdvice
 # Table of contents
1. [Background and Problem Statement]
2. [Data Cleaning]
3. [EDA and Data Visualisation]
4. [Modelling]
5. [Conclusion and Recommendations]
# Background
Smart Pet is a company made up of former vets, pet store owners and animal shelter volunteers. During the COVID-19 pandemic, there was an increase in pet ownership as people turned to animals as a form of companionship. Most commonly owned pets consist of dogs and cats. With the increase of pet owners, there is also an influx of naive owners with a lack of access to local resources for pet care in Singapore. We will be presenting an application to fellow vets, pet store owners and volunteers in the animal industry to create a model that classifies whether a post is dog or cat related. 
The data collection team has scrapped data from DogAdvice and CatAdvice for our model learning.
# Problem Statement
An influx of inexperienced pets owners overly reliant on vets and pet store reduces work efficiency, how can we optimize it?
|Model|Vectorizer|Train Score|Test SCore|Specificity|F1 Score|
|---|---|---|---|---|---|
|**KNN**|CountVectorizer|0.90|0.83|0.47|0.83|
|**KNN**|TDIFVectorizer|0.81|0.77|0.41|0.77|
|**Nominal Naive Bayers**|CountVectorizer|0.98|0.96|0.95|0.96|
|**Nominal Naive Bayers**|TDIFVectorizer|0.71|0.72|0.02|0.72|
|**Logistic Regression**|CountVectorizer|0.99|0.97|0.93|0.97|
|**Logistic Regression**|TDIFVectorizer|0.71|0.72|0.02|0.72|
|**Random Forest**|CountVectorizer|0.99|0.97|0.94|0.97|
|**Random Forest**|TDIFVectorizer|0.84|0.83|0.53|0.82|

# Conclusion and Recommendations
As we can see the weakest performing model are `Logistic Regression` + `TDIF` and `Nominal NB` + `TDIF`, so we will be using that as the baseline model to compare our results.
Our Top Performing model are `Logisitic Regression` + `CVEC` and `Random Forest` + `CVEC`. 
The top words that influence the prediction of a post being classified are `puppy`, `pup` and `mix`. A post will be more likely to be classified into a DogAdvice subreddit with the unique keywords and the remaining posts will be classified into CatAdvice posts.
During EDA, majority of DogAdvice post were asking for advice for caring of older dogs, with words such as anxiety and depression. Majority of CatAdvice posts were asking for advice for caring of new and young cats.
# Model Limitations
The Naive Bayers works under the theoretical impression that the features are unique and independent of each other, however that is not always feasible in real world settings. Due to time constraint, only a small subset of data 2000 were collected from the Reddit, and there is a chance of bias to certain topics that have been repeated during the collected time period. The origin of users posting onto Reddit might influence the purpose of their posts as different countries (different pet regulations) might have an influence keywords used in posts.
Majority of DogAdvice posts contain visual media in the form of pictures or videos whereas there is a lack of visual media in CatAdvice, as the Cat subreddit has a stricter regulation. One of the regulation of the CatAdvice restricts users from asking medical advice, which might explain the lack of posts regarding older cats, as older animals have a greater need for medical advice than young kittens.