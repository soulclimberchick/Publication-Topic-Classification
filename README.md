# CATALOGIQUE
### PUBLICATION TOPIC CLASSIFACTION
#### We organize your stuff so you don't have to

# What We Solve:
#### problem statement:
Our client at Elsevier is looking for a better way to clasify their scientific articles. Elsevier helps researchers and healthcare professionals advance science and improve health outcomes for the benefit of society. (soruce: https://www.elsevier.com/about). With the large volume of scientific research articles flowing into the pipeline, we expertly classify and store your data for quick and efficient searching.


## Data Collection:
For our example product, we collect approximately 3,000 posts each from both the Physics and Biology subreddits on reddit.com. We utilize reddit's pushift api (source: https://github.com/pushshift/api) to scrape these subreddits with parameters aimed at ignoring deleted content and keeping the most recent of posts. CATALOGIQUE believes training on recent data will help keep our models up to date and improve accuracy over time. For modeling purposes, we parsed the data down to just the titles.

## Exploratory Data Analysis (EDA) and Modeling
Once the data is ingested into our database, we then perform exploratory data analysis to make sure we have what we need. We then clean the data and rid the titles of unnecessary punctutation, capitalization and so on. Once our data is clean, we take a quick peak at initial findings before any modeling to set a baseline. 

When we are satisfied with the initial data cleaning, the datasets are then saved and imported into our Code notebook where we combine the datasets and begin the real EDA. Here, we utilize many models to find the best fit. Models with their current scores include:

|Model                |Scores                         |Score Tyoe                        
|----------------|-------------------------------|-----------------------------|
|Logistic Regression|`74%`            |cross_val_score           |
|Linear Regression|`-1.15`            |R2 Score            |
|Count Vectorizer|`79%`|F1 Score|
|Tfidf Vectorizer|`78%`            |F1 Score           |
|Multinomial Nïve Bayes w/ Tfidf|`78.8%`            |F1 Score|
|Random Forest|`78%`|-- is en-dash, --- is em-dash|
|KNN w/ CV|`65%`            |cross_val_score|
|KNN w/ Tfidf|`63%`            |cross_val_score|
|Confusion Matrix|`|629|133| over |214|538|`|tp,fn over fp,tn |

We tested many iterations with many different stop-word combinations. We chose the Count Vectorizer model as the results were balanced between all scores and had the highest scoring. This is great because Count Vectorizers are wonderfully efficient models for our use case!

## Recommendations:

More refining of stop-words is recommended. We may also want to try adding in comments for training and testing the model as this will bring in more potentially useful vocabulary. If that route is chosen, careful attention to variance will be advised. 

## Why you need us:
**Our services will save you time and money by streamlining your data ingestion, sorting and storage.**

Accurate Results:
**With our expertly curated models, you will see accurately sorted articles that are easy to find**

Adaptability:
**Our models will be thoroughly tested utilizing the latest training data. Customized to work for any set of articles you wish to classify!**

Our Promise:
**While our example model sits at 79% f1 score, with our expertly curated models, you will see even better, more accurately sorted articles that are easy to find!**

Continuous Improvements:
**We will continue to fine tune parameters and stop-words to find the perfect balance of accuracy and efficiency**

# We organize your stuff so you don't have to