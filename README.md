# PJ1_Youtube_Trending_Video_Analysis

# 1. Introduction
## 1.1 What is Youtube? 
    
**YouTube** is a free video sharing website that makes it easy to watch online videos. You can even create and upload your own videos to share with others. Originally created in 2005, YouTube is now one of the most popular sites on the Web, with visitors watching around 2.6 billion users worldwide as of 2022. It's ranked as the second-most popular social network, and the only platform that has more active users than YouTube is Facebook.
    
## [1.2 Context](https://www.kaggle.com/datasets/datasnaek/youtube-new) 
    
YouTube (the world-famous video sharing website) maintains a list of the top trending videos on the platform. According to Variety magazine, "To determine the year's top-trending videos, YouTube uses a combination of factors including measuring users interactions (number of views, shares, comments and likes). Note that they're not the most-viewed videos overall for the calander year". Top performers on the YouTube trending list are music videos (such as the famous virile "Gangam Style"), celebrity and/or reality TV performances, and the random dude-with-a-camera viral videos that YouTube is well-known for. 
    
This dataset is a daily record of the top top trending YouTube videos. 
    
Note that this dataset is a structurally imporved version of [this dataset.](https://www.kaggle.com/datasnaek/youtube)
    
## [1.3 Content](https://www.kaggle.com/datasets/datasnaek/youtube-new)
    
This dataset includes several months (and counting) of data on daily trending YouTube videos. Data is included for the US, GB, DE, CA, and FR regions (USA, Great Britain, Germany, Canada, and France, respectively), with up to 200 listed trending videos per day. 
    
EDIT : Now includes data from RU, MX, KR, JP, and IN regions (Russia, Mexico, South Korea, Japan and India respectively) over the same time period. 
    
Each region's data is in a separate file. Data includes the video title, channel title, publish time, tags, views, likes and dislikes, description, and comment count. 
    
The data also includes a 'category_id' filed, which varies between regions. To retreive the categories for a specific video, find it in the associated JSON. One such file is included fore each of the five regions in the dataset. 
    
For more information on specific columns in the dataset refer to the [column metadata.](https://www.kaggle.com/datasnaek/youtube-new/data)
    
## 1.4 Features 
    
- video_id : Unique code of video 
- title : Title of video 	
- publishedAt : Published time of video 
- channelId : Unique code videoof youtube channel 
- channelTitle : Title of youtube channel
- categoryId : Unique code of category
- trending_date : Trending date of video 	
- tags : Tag of video
- view_count : Total view of video 
- likes : Counts of people like the video 
- dislikes : Counts of people dislike the video 
- comment_count : Counts of people comment on the video 
- thumbnail_link : Linkes of tunmbnails of the video 
- comments_disabled : Whether people can leave comments 
- ratings_disabled : Whether people can leave ratings 
- description : Description of video 

# Project1 : Time Comparison of EDA Python vs Pandas 

**Pandas** is a software library written for the Python programming language for data manipulation and analysis. In particular, it ofers data structures and operations for manipulating numerical tables and time series. Pandas is mainly used for data analysis and associated manipulation of tabular data in DataFrames. Pandas allows importing data from various file format such as CSV, JSON, SQL, and Excel.

In this project, we will analyze data using Python and compare execution time using Pandas module. It's obvious that data analysis using Pandas is more faster than using general code, because Pandas module is bulit on C. 

When we import dataset, importing data using python takes about 552.80s and importing data using pandas takes about 1.29s. Importing dataset using pandas more faster than about 427 times using python!

| Contents | Execution time using Python | Execution time using Pandas | Execution ratio of Python vs Pandas | 
|:---:|:---:|:---:|:---:|
|Time Comparison of Importing Dataset | 552.8068583011627 | 1.292646884918213 | 427.65496497996776 | 
|Question1| 0.06637978553771973 | 0.029551029205322266 | 2.246276604327691 | 
|Question2| 0.06817150115966797 | 0.040929555892944336 | 1.665581257172149 | 
|Question3| 0.16998028755187988 | 1.3795523643493652 | 0.12321408881934486 | 
|Question4| 0.1865525245666504 | 1.4438941478729248 | 0.1292009700582765 | 
|Question5| 0.04221820831298828 | 0.007451057434082031 | 5.66606937156022 | 
|Question6| 0.10105609893798828 | 0.04294633865356445 | 2.3530783323155497 | 
|Question7| 1.9336814880371094 | 0.9797186851501465 | 1.9737109410552516 | 

When we explore dataset through seven questions, EDA using pandas are more faster than using python excepting question 3 and 4. Because pandas is module build on C, using pandas while we do data analysis is more efficiently on time and cost. 

# Project2 : Preprocessing_Files_on_CLI 

**Data Munging**, sometimes refereed to as **data munging**, is the process of transforming and mapping data from one "raw" data form into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics. The goal of data wrangling is to assure quality and useful data. Data analysts typically spend the majority of their time in the process of data wrangling compared to the actual analysis of the data. 
    
In this project, purpose of the project is wrangling files in /Dataset merging files by continents. At first, I only use head, tail and redirection command for our purpose. Workprocess of the first task is same as below. 

1. Make new empty file with echo and touch command. 
2. Extract column from one file and attach to new empty file using head -n +1 command. 
3. By continent, attach dataset using tail -n +2 command.
4. Lastly, check the result using wc -l command. 

In second, I only use CSVkits command to do same works. CSVkit is a suite of command-line tools for converting to and working with CSV, the king of table file formats. We can do same task of workflow 1, 2, 3 above using below commands. 

```BASH 
# Merge SA_youtube_trending_data.csv 
!csvstack -n country -g "Brazil,Mexico" Dataset/BR_youtube_trending_data.csv Dataset/MX_youtube_trending_data.csv > Wrangled_Dataset/SA_youtube_trending_data2.csv 
```
