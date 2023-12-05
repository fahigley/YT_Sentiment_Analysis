# YouTube Sentiment Analysis

## Introduction
With around 3.7. million videos uploaded each day and over 1 billion hours watched every day it is safe to say that YouTube is the most popular video streaming site on the internet. While the videos uploaded are heavily analyzed by YouTube for any inappropriate content, the comments are not given the same attention. Are these YouTube comment sections war zones of malice just for arguing and degrading others, or are they positive and constructive environments where people can speak freely? With the use of sentiment analysis, it is possible to find out truly how positive (or negative) the YouTube comment section is.

## Questions
1. In general, do YouTube comments lean towards a more positive or negative sentiment? 
2. Which genre of YouTube videos tends to attract the most positive feedback in the comments section? 
3. What is the sentiment towards controversial topics on YouTube?

## Gathering Data
The data was gathered using the YouTube Data V3 API. This API allows the user to get lots of public data about videos such as comments, view counts, likes, dislikes, etc. In order to gather the data the ``get_youtube_comments()`` function was used. This Function uses the ``googleapiclient.discovery`` toolkit to request youtube comments for a particular video ID from the API. This function was challenging to write having never used the API before, however once I got used to it development continued rapidly. In order to feed ``get_youtube_comments()`` specific video IDs they were all stored in arrays. The specific video ids were chosen by random sources. All videos are among the top videos in their category based on view count. The 6 categories were chosen by popularity on the platform, Gaming, Vlog, Music, Beauty, Reaction, and Controversial. The Controversial category consisted of multiple videos from multiple viewpoints of the Israel-Hamas conflict as it is very hot topic as of November 2023. After the comments were gathered they are stored in an array. The ``toCSV()`` takes this array of comments and puts them into a csv file. Each genre was put into its own data CSV. The data was then cleaned using ``clean_csv()``. Being a global website YouTube comments are in many different languages. The langid python library was use to filter the comments to english comments only. These comments were put into their own CSV files to keep the raw and clean data separate. Once the data was gathered and cleaned it was ready for sentiment analysis.


## Methods
Tools for gathering data/data manipulation
- googleapiclient - gathering data from YouTube comments
- pandas - to read csv and manipulate data
- csv - creating and populating csv files
- langid - filtering comments based on language

Tools for Sentiment analysis of comments
- numpy - array manipulation and math
- NLTK - sentiment analysis
- TQDM - progress bar

## Results

## Discussion

