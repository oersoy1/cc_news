# cc_news

Repo for demonstrating NLP Fundamentals on Common Crawl News Corpus

### Requirements:

1. Insall AWS CLI on the machine if it does not exist
2. Create an environment using the environment.yml file provided
3. Install pyspark and Java Runtime in case missing

Here are highlights of each Notebook:

#### 1_eda:
Basic Exploration of files available on the CC_News [Dataset](https://commoncrawl.org/2016/10/news-dataset-available/) for the month of December 2019
1. extracted some high level meta data from the corpus
2. Performed some basic EDA
3. Were able to pull the text data and detect the language on it.
4. Extracted the English Domains
5. On a high level classified these English domains included in the set into 6 main categories.
6. And did some parallelization to speed up the process

#### 2_extract_all_data_spark:
Mainly, in Spark, we
1. Ran through the corpus with our classified English domain list
2. Filtered out other domains that are most likely not news channels.
3. From the individual webpage, scraped title description and keywords if there are any and the body content.
4. Created a Data Frame to perform more NLP

#### 3_feature_engineering:
1. Using the keywords from the meta data tags of the web pages, created class labels.
2. Did some basic preprocessing for modeling
3. Train and test split
4. Persist the data

#### 4_classification_bert:
1. created our inmput features for BERT in a parallel format
2. fine tuned a decent BERT classifier that does pretty good on the documents
3. Extracted some records to be used in Topic Modeling

#### 5_topic_modeling
Performed LDA to find some of the most commonly talked about topics in the news given a main topic area like "politics"

