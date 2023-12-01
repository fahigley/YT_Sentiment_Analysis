# YT_Sentiment_Analysis

## Introduction
With around 3.7. million videos uploaded each day and over 1 billion hours watched every day it is safe to say that YouTube is the most popular video streaming site on the internet. While the videos uploaded are heavily analyzed by YouTube for any inappropriate content, the comments are not given the same attention. Are these YouTube comment sections warzones of malice just for arguing and degrading others, or are they positive and constructive environments where people can speak freely? With the use of sentiment analysis, it is possible to find out truly how positive (or negative) the YouTube comment section is.

## Questions
1. In general, do YouTube comments lean towards a more positive or negative sentiment? 
2. Which genre of YouTube videos tends to attract the most positive feedback in the comments section? 
3. What is the sentiment towards controversial topics on YouTube?

## Data
The data was collected using the YouTube Data v3 API provided by Google. This API allows the user to collect a lot of data about a video, such as the comments from a video, using its video ID. The specific YouTube videos were selected based on popularity and primary language; many of the most popular videos in each category are videos from non-English speaking countries therefor most of the comments were not in English. 4-5 of the top videos were selected for each category. The categories being Gaming, Vlogs, Music, Beauty, and Reaction. Some categories had more than enough comments in just one videos. So, the maximum comments allowed per video was 50,000. After the comments were gathered into their own files the non-English comments, if any, were removed using the python package langid. The cleaning of the data was not 100% correct. Some of the comments that were English were removed so the sentiment analysis will be performed on both the raw and cleaned versions of the csv and results analyzed. There will also be controversial videos that will be gathered. To answer the question 3. The data had to be collected throughout the course of multiple days due to the quota that Google had on number of queries per day.

## Methodology
1.	Gather data using YouTube Data v3 API
    -   Put data into a csv file. One per genre
    -	Clean csv files
2.	TensorFlow Sentiment analysis
    -	Create model
    -	Train and test model
    -	Use model on gathered comments

3.	Results
    -	Visualize results to answer questions and draw conclusions
    -	Write report



