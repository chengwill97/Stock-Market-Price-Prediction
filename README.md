#### Table of Contents
1. Project Description
2. Installation Instructions

# <h60><center> Massive Data Storage, Retrieval, and Deep Learning 198:543 <br> Project Final Report

## <center> Technology Stock Prediction Using Website Traffic and Sentiment of News Articles.

## <center> Is there a Correlation between Stock Prices of Technology Companies, Online Web Traffic, and Sentiment of News and Financial Articles?

<hr>

### Authors

**Akash Desai, RU Fall'18 CS and Applied Sciences in Engineering**
<br>
![Akash Graduated][akash_graduated]

[akash_graduated]: ./img/graduated-100%-brightgreen.svg "Akash graduated Fall 2019"

**William Cheng, RU Spring'19 CS and Physics**
<br>
![William Graduated][william_graduated]

[william_graduated]: ./img/graduated-88%-green.svg "Akash graduated Fall 2019"

### Description

As financial market is one of most sought after fields and with its readily available time series data, it made us dive deeper and see if the number of visits for a company page on Wikipedia which meant there was some ongoing "buzz" about the company, affected the price of its stock, this idea was further reinforced by whether there was good sentiment towards the company in news articles published during that time.
<br>
We choose this project, because we saw the simplicity that existed within time series datasets. As there are so many different applications where this can be applied, exploring this field seemed really fascinating. Finding patterns in available dataset and seeing if we can better predict with conjunction another dataset is quite interesting.  Below we can see the immense growth of the time series data set.

### Preprocessing

##### Data Exploration - News Articles in Prediction:
We want to look at how influential news articles are to the movement of stocks of technology companies. News articles are read by many people and may influence the thoughts and actions of others, especially stock traders. This is due to the fact that news articles are one of the main sources that people receive information.
<br>
<br>
We want to look at the sentiment of news articles, meaning the polarity and subjectivity of the news articles, so we run sentiment analysis on the content within news articles.
<br>
<br>We also want to make sure that the news articles that we have in our dataset are related to technology companies, so we use cosine similarity analysis to look at how related a news article is to keywords that relate to technology companies. We reduce the runtime cost of running cosine similarity analysis on all the text of news articles by finding at most 30 words with the highest TFIDF scores.
<br>
<br>
In the end, the dates, polarity scores, subjectivity scores, and cosine similarity scores are all processed to be used as part of the dataset to trian our Technology Stock Prediction Model.

##### Data Exploration - Wikipedia

We used the Wikipedia in order assess the online web traffic. The dataset contains over 145063 articles with its traffic number from 2015 to 2016 which is over 550 columns of data for every column. We used pandas library to handle all the data manipulation.


Exploration, can we find some pattern in the underlying website traffic dataset?


After flattening the data, by filtering and really "massaging" the data we were able to a clean the dataset. As there were duplicate articles we were able to group and take the mean of the visitor for a page for a particular day.

We wanted to experiment with just predicting the number of views a Wikipedia page gets in the future, we thought it would be interesting to find out regarding this topic due to its application web traffic monitoring, if we think an anomaly is going to happen by looking one step further we can actually be ready for such event in time of higher traffic for a website, making the website more robust.

**Moving Average:**
We started off with the naive method which relied on y(t+1) = y(t), as it a naive solution its not the most accurate, and we can see in the graph below. Then other methods we experimented with were an average of entire graph which lead to prediction that were really off, then we use rolling mean with window of n variables in the past that gave a better estimate as you can see that below.

**Exponential Smoothing:**
Later used which weighted the data point weaker as we further away from those points. Lastly, with the help Holts trend, we wanted to see if we could find any trend with our data. We graphed the Trend, Seasonality and Residual below and if there is a particular trend seen in the dataset we can use the holt winter method, however we weren’t able o see any particular trend but we saw a pattern in seasonality and so we carried on to the most popular method which is the Sarima. Sarima aka Seasonal Autoregressive Integrated Moving average where we saw closeness to the dataset

### Quick Summary of Results

##### Discussion:
From the bar plots of the metrics below, it can be seen that the Amazon Finance + Wikipedia Visits datasets were the most impactful in terms of having the lowest error across the board **Mean Absolute Error**, **Mean Squared Error**, **Median Absolute Error**, as well as the highest **R2** Score. However, it does have a higher variance score than the rest of the datasets.

![alt text][dl_results]

[dl_results]: ./img/dl_results.png "Deep Learning Results"

![alt text][dl_metrics]

[dl_metrics]: ./img/dl_metrics.png "Deep Learning Metrics"

## Getting Started

Clone the repository or download the zip:
```
git clone https://github.com/chengwill97/Stock-Market-Price-Prediction.git
```

### Prerequisites

Software:
- python3.6
- Anaconda/Miniconda Package Manager

Miniconda will only install the minimum required packages to run python and you can install the rest of the packages using our environment.yml file :)

1. Make sure you have Anaconda/Miniconda or install it here
<br>
<a href="https://docs.anaconda.com/anaconda/install/">Anaconda Installation Instructions</a>

### Installing

1. Go into the directory where you cloned this repository
```
cd /path/to/Stock-Market-Price-Prediction
```
2. Create a new conda environment based off the environment.yml with the following command
```
conda install -f ./environment.yml
```