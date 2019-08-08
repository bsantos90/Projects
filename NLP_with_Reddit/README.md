# Natural Language Processing with Reddit

#### Project by: Bruno Santos

### Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data](#Data)
- [Conclusion and Recommendations](#Conclusion-and-Recommendations)

## Problem Statement

We have been tasked with a two-fold problem: the first part is to use web-scraping and our knowledge of APIs to access data from reddit - specifically two separate subreddits - and properly convert that data to CSVs. We will need to gather sufficient data for our models and utilize this data later on to build and fine-tune our models. The second part will envolve using Natural Language Processing and appropriate binary classification models to accurately predict what subreddits our posts originated from.

How accurately will each individual model perform? Are there certain parameters that have a strong impact in the performance and overall accuracy of our models? In hindsight, what could we have done differently to have our models perform better, or to make the project better in general?

## Executive Summary

Reddit - often referred to as "the front page of the internet" - is "an American social news aggregation, web content rating, and discussion website" according to Wikipedia. Users congregate in sections of the website, referred to as "subreddits", which group posts by their subject-matter. For example, /r/politics is a subreddit dedicated to political discussion, /r/hockey is a subreddit dedicated to hockey-related discussion, and so on.

Our focus was on the PersonalFinance subreddit and the LegalAdvice subreddit. The former describes itself as a place to "get your financial house in order, learn how to better manage your money, and invest for your future". The latter can be described as "a place to ask simple legal questions". While at first glance there does not to be much similarity between the two, often times legal matters and financial matters cross into the realm of one another. That is to say - financial matters often have legal implications, and legal matters often have financial implications.

We gathered data from 3,367 total posts - 1840 of those from the LegalAdvice subreddit (54.65%), and 1527 from the PersonalFinance subreddit (45.35%). Given the format in which we obtained these posts, a significant amount of cleaning had to be done to prepare the posts for modeling and visualization. Using text feature extraction tools from Python's Sci-Kit Learn library, we broke the post titles down into individual words to pass through our models. We then built and fine-tuned a number of different models to see how accurately they would be able to predict what subreddit a post originated from using the language contained within the title of the post. 

## Data

Our data was scraped from the [legaladvice subreddit](https://www.reddit.com/r/legaladvice) and the [personalfinance subreddit](https://www.reddit.com/r/personalfinance).

Our collected data in CSV format can be found [here](./Data)
The notebook with our process of data collection can be found [here](./Data-Collection-Reddit.ipynb)

## Conclusion and Recommendations

In conclusion, all of our models fared better than the "null model" of 54.65%, with accuracy scores on previously unseen testing data ranging from roughly 80% to 86%. We had models that ranged between 1000 - 3000 "features", or words, used by our models to make their predictions. As was to be expected, our models that we GridSearched through to fine-tune hyperparameters performed better than simpler models. Our Multinomial Naive Bayes model had the best overall performance, with training accuracy of 91.17% and testing accuracy of 86.25% - a discrepancy of less than 5%.

Looking over our list of Vectorized words, we find that our initial hypothesis that the two subreddits would have some significant overlap does not seem to be as accurate as we had predicted. The most common words used in both subreddits are unique to each individual subreddit - there does not appear to be overlap in those words. The importance of specific words can be directly traced back to the subreddit of origin based on the implications. That said, there are several words that we find throughout both subreddits a fairly significant number of times.

In hindsight - I would likely look at subreddits that had a more direct correlation rather than a supposed implied correlation. While our models had very high accuracy scores, this can likely be attributed to the fact that there are very distinct words used in each individual subreddit. Using subreddits that have a more direct correlation - and therefore more similar language - would add a layer of difficulty to the project, while at the same time giving us further insight into how language can be used to make determinations when there are such strong similarities.