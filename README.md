# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web API & Neuro-linguistic programming (NLP

### Overview

- The main objective of this project is to scrape two sub-reddits and develop models (machine learning) to distinguish a post came from which sub-reddit.

### Problem Statement

- This project aims to develop a classification model to distinguish two subreddits with linked connections. The two sub-reddits that will be scraped are Genshin Impact & Honkai Impact 3, which are games developed by Mihoyo. These two games contain characters which are available in both games and will challenge the accuracy of the model. 
-----

### About the Data

- Data is scraped from these two sub-reddits using Web API [(Pushshift API link)](https://github.com/pushshift/api):

- Genshin Impact   
https://www.reddit.com/r/genshin_impact/

- Honkai Impact 3  
https://www.reddit.com/r/honkaiimpact3/


### Data Preparation

- Null values were replaced with '0' as a string.
- Title, Selftext, and Subreddit features were retained.
- Punctuations were removed using NLP & Regex.
- Genshin Impact encoded to 0.
- Honkai Impact encoded to 1.

### Key Features
 - subreddit (interger: 0 | 1)
 - title (String)

### Additional Features

Over 10,000 additional features derived from the word content in title & selftext, created by using CountVectorizer .

------

### Modelling & Evaluation
 
 Two pipelines were developed and used in the modelling:
 
 <b>First Pipeline:</b>
 - CountVectorizer
 - RandomForests
 
 ![](https://git.generalassemb.ly/tim-kozaki/dsif2_projects/blob/master/project_3/images/randomforests_results.png)
 ![](https://git.generalassemb.ly/tim-kozaki/dsif2_projects/blob/master/project_3/images/randomforests_matrix.png)
 
 <b>Evaluation Results:</b>
 5-fold Cross validation score: 0.74   
 Training score: 0.99    
 Testing score: 0.78    
 Grid Search (Best score): 0.74   
 Specificity: 0.74    
 Accuracy score: 0.78   
 ROC AUC: 0.87   
 
 <b>Second Pipeline:</b>
 - CountVectorizer
 - MultinomialNB
 
 ![](https://git.generalassemb.ly/tim-kozaki/dsif2_projects/blob/master/project_3/images/multinomialnb_results.png)
 ![](https://git.generalassemb.ly/tim-kozaki/dsif2_projects/blob/master/project_3/images/multinomialnb_matrix.png)
 
  <b>Evaluation Results:</b>
 5-fold Cross validation score: 0.78   
 Training score: 0.95    
 Testing score: 0.81    
 Grid Search (Best score): 0.78   
 Specificity: 0.82    
 Accuracy score: 0.81   
 ROC AUC: 0.90   


 -----
 
 ### Future Improvements
 
- Identify and develop keywords used uniquely for each subreddit. For example, unique character names in each game.
- Address overfitting of the models.
- Train and test the data with other models.
