# YouTube Comment Sentiment Analysis

## Introduction
With around 3.7. million videos uploaded each day and over 1 billion hours watched every day it is safe to say that YouTube is the most popular video streaming site on the internet. While the videos uploaded are heavily analyzed by YouTube for any inappropriate content, the comments are not given the same attention. Are these YouTube comment sections war zones of malice just for arguing and degrading others, or are they positive and constructive environments where people can speak freely? With the use of sentiment analysis, it is possible to find out truly how positive (or negative) the YouTube comment section is.

## Questions
1. In general, do YouTube comments lean towards a more positive or negative sentiment? 
2. Which genre of YouTube videos tends to attract the most positive feedback in the comments section? 
3. What is the sentiment towards controversial topics on YouTube?

## Gathering Data
The data was gathered using the YouTube Data V3 API. This API allows the user to get lots of public data about videos such as comments, view counts, likes, dislikes, etc. In order to gather the data the ``get_youtube_comments()`` function was used.

<img src="graphs/code/get_youtube_comments.png" alt="getYouTubeComments Function"/>

This Function uses the ``googleapiclient`` toolkit to request youtube comments for a particular video ID from the API. This function was challenging to write having never used the API before, however once I got used to it development continued rapidly. In order to feed ``get_youtube_comments()`` specific video IDs they were all stored in arrays. The specific video ids were chosen by random sources. All videos are among the top videos in their category based on view count. The 6 categories were chosen by popularity on the platform, Gaming, Vlog, Music, Beauty, Reaction, and Controversial. The Controversial category consisted of multiple videos from multiple viewpoints of the Israel-Hamas conflict as it is very hot topic as of November 2023. After the comments were gathered they are stored in an array. The ``toCSV()`` takes this array of comments and puts them into a csv file. 

<img src="graphs/code/to_CSV.png" alt="toCSV function" width="500" />

Each genre was put into its own data CSV. The data was then cleaned using ``clean_csv()``. 

<img src="graphs/code/clean_csv.png" alt="cleanCSV function" width="500" />

Being a global website YouTube comments are in many different languages. The langid python library was use to filter the comments to english comments only. These comments were put into their own CSV files to keep the raw and clean data separate. Once the data was gathered and cleaned it was ready for sentiment analysis.

## Methods
Tools for gathering data/data manipulation
- googleapiclient - gathering data from YouTube comments
- pandas - to read csv and manipulate data
- csv - creating and populating csv files
- langid - filtering comments based on language
- numpy - array manipulation and math functions

Tools for Sentiment analysis and visualization
- NLTK - sentiment analysis
- TQDM - progress bar
- matplotlib - data visualization

The sentiment analysis of the YouTube comments was done using the ``sentiment_analysis()`` function. 

<img src="graphs/code/sentiment_analysis.png" alt="sentiment_analysis function" width="500" />

This function uses the built in NLTK ``SentimentIntensityAnalyzer()`` function to analyze the sentiment of each comment in a given csv. This function return 3 different values, the positive polarity, the negative polarity and the compounded polarity. This analysis a polarity greater zero was deemed as positive, a polarity less than zero was deemed as negative, and a polarity of 0 was neutral. This was done so that all the comments would be either positive negative or neutral. This was done with every comment in a given csv adn added to the array ``sent``. This data was then totaled up per video. This portion of was done with the ``get_sent_totals()``.

<img src="graphs/code/get_sent_totals.png" alt="get_sent_totals function" width="250" />

## Results and Discussions

### Question 1 | In general, do YouTube comments lean towards a more positive or negative sentiment? 
In order to answer this question the whole data set must be taken into account. To do this, all the positive data was added up based on positive, negative and neutral comments. Then the percentages were calculated for both the clean and raw data. The analysis of both the raw and clean data was taken to see the discrepancies between the both.

<img src="graphs/PICharts/clean/total_clean_pi.png">
<img src="graphs/PICharts/raw/Total_raw_pi.png">

With 59% neutral for the raw data and 70% for the cleaned data it is clear that the majority of comments on YouTube are neutral. After the neutral 30% of the raw and 25% of the clean comments are positive, followed by 10% and 3% for the negative percentage of the raw and clean respectively. Youtube is primarily neutral and positive. With approximately 10% or less of negative comments on the site, it is safe to say that YouTube is an overall positive website. 

### Question 2 | Which genre of YouTube videos tends to attract the most positive feedback in the comments section?

#### Beauty

#### Controversial

#### Gaming

#### Music

#### Reaction

#### Vlog


### Question 3 | What is the sentiment towards controversial topics on YouTube?





