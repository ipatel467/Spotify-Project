# Spotify Song Popularity 
#### by Ibrahim Patel


## Executive Summary
For this project, I mainly wanted to use Spotify's API. After getting authorization I began to explore the API and see the different types of song data that was being collected. I pulled 1000 songs from Spotify's API along with their respective popularity. This column will be very important later on in the experiment. 

![Alt Text](https://media.giphy.com/media/lqxxKmzFXFDyw/giphy.gif)

## Contents
1. [Introduction](#introduction)
    - [Problem Statement](#problem_statement)
    - [Dataset](#dataset)
2. [Analysis](#analysis)
    - [Data Cleaning](#data_cleaning)
    - [Exploratory Data Analysis](#exploratory_analysis)
    - [Modeling](#modeling)
    - [Results](#results)

## Introduction <a name="introduction"></a>


<p></p>

<p></p>

### Problem Statement <a name="problem_statement"></a>
A song conisist of many different audio features such as artist, danceability, energy, tempo, acousticness,etc, but we want to see if these feature will help predict the popularity outcome of the song. 

### Dataset <a name="dataset"></a>
I first had to pull the data from Spotify's API. I first had to pull specific songs along with their popularity and other features. After pulling the song information I began to pull the specific audio features from the song such as danceability, energy, tempo, etc. 

## Analysis <a name="analysis"></a>

### Data Cleaning <a name="data_cleaning"></a>

There were some songs that contained N/A for certain columns. I had to drop a certain column because the majority of songs were considered N/A in that column. Overall the data was clean for the most part and took minimal time for cleaning. 

### Exploratory Data Analysis <a name="exploratory_analysis"></a>
<p>
The first feature we will be looking at today is the Duration feature. Duration is just simply the time length of the song. Spotify's API calculates songs by Milliseconds, so we will have to convert them into minutes. Below is a distribution of the different song durations in the dataset.
 
</p>


<p>
<img width="762" alt="Screen Shot 2020-12-16 at 11 30 17 AM" src="https://user-images.githubusercontent.com/52756457/102386903-54c7f680-3f95-11eb-8699-0dca9e50831c.png">
</p>



<p>
In the histogram above we can see that the distribution looks somewhat normal. We can see that the mean song Duration in Milliseconds is about 200K. This is roughly a 3mins and 20second song. A song that has 300K milliseconds or more is a 5-minute song or longer. Overall this makes sense because most people don't listen to extremely long songs.
</p>


One interesting feature I wanted to take a look at was Tempo. The tempo is the speed or pace of a given piece and derives directly from the average beat duration. In simple words, the tempo is just the speed or pace of the song. Is it a slow singing song, or a fast rap song?


<img width="766" alt="Screen Shot 2020-12-16 at 11 30 50 AM" src="https://user-images.githubusercontent.com/52756457/102386815-39f58200-3f95-11eb-9c43-01683ae6f8c1.png">

Looking at the distribution we can see that the median is around 90-100. Overall this is saying that the majority of the songs in this dataset have a slow tempo rather than a fast one. If we look at the tempo of 200 we can see there is a very low frequency. However, all the other tempos after 100 seem to have a similar but slightly varying freuency.

### Modeling <a name="modeling"></a>

![Alt Text](https://media.giphy.com/media/1zi2FQvx8c6jXZB9dm/giphy.gif)



### Results <a name="results"></a>


 

<p>My second best performing model was the Gradient Boosting model. The Gradient Boosting model has a R_Squared of 0.527. This means this model is capturing almost 53% of the data needed to predict a song's popularity. This model performed slightly better than the XGBoost.</p>


<p>
<img width="732" alt="Screen Shot 2020-12-16 at 11 48 44 AM" src="https://user-images.githubusercontent.com/52756457/102387227-ba1be780-3f95-11eb-84b4-fd719bc27583.png">
</p>


<p>Last but not least, below is the code for the AdaBoost model. This was the best performing model in comparison to all the other models. This AdaBoost model gave me a R_squared of 0.612 which once again means this model is gathering 61% of the data needed to predict a song's popularity. </p>



<p>
<img width="729" alt="Screen Shot 2020-12-16 at 11 48 25 AM" src="https://user-images.githubusercontent.com/52756457/102387146-a2dcfa00-3f95-11eb-92ff-a00337d8c3de.png">
</p>





To view the full extent of my work you are more than welcome to browse through the notebook. To get a better understanding of my findings to feel free to read my blog at 
https://www.ibbysblog.com/. 

I will work on this project in the future, and try my best to make my model better by doing more feature engineering.


