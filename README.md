# <h60><center> Massive Data Storage, Retrieval, and Deep Learning 198:543 <br> Project Final Report

### <center> Professor Gerard de Melo

### <center> By Akash Desai and William Cheng

## <center> Technology Stock Prediction Using Website Traffic and Sentiment of News Articles.

## <center> Is there a Correlation between Stock Prices of Technology Companies, Online Web Traffic, and Sentiment of News and Financial Articles?

<hr>

### Description

As financial market is one of most sought after fields and with its readily available time series data, it made us dive deeper and see if the number of visits for a company page on Wikipedia which meant there was some ongoing "buzz" about the company, affected the price of its stock, this idea was further reinforced by whether there was good sentiment towards the company in news articles published during that time.
<br>
<br>
We choose this project, because we saw the simplicity that existed within time series datasets. As there are so many different applications where this can be applied, exploring this field seemed really fascinating. Finding patterns in available dataset and seeing if we can better predict with conjunction another dataset is quite interesting.  Below we can see the immense growth of the time series data set.

### Quick Summary

##### Discussion:
From the bar plots of the metrics below, it can be seen that the Amazon Finance + Wikipedia Visits datasets were the most impactful in terms of having the lowest error across the board **Mean Absolute Error**, **Mean Squared Error**, **Median Absolute Error**, as well as the highest **R2** Score. However, it does have a higher variance score than the rest of the datasets.

![alt text][dl_results]

[dl_results]: ./img/dl_results.png "Logo Title Text 2"

![alt text][dl_metrics]

[dl_metrics]: ./img/dl_metrics.png "Logo Title Text 2"

## Getting Started

Clone the repository or download the zip:
```
git clone https://github.com/chengwill97/Stock-Market-Price-Prediction.git
```

### Prerequisites

Software:
- python3.6
- Anaconda/Miniconda Package Manager
<br>
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