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


pics of dur in milisec song

paragraph

pic of tempo

para graph 

### Modeling <a name="modeling"></a>

![Alt Text](https://media.giphy.com/media/1zi2FQvx8c6jXZB9dm/giphy.gif)



### Results <a name="results"></a>


 

<p>Now that we have seen the results of the model, lets see how different features played a role in predicting the happiness score.</p>


<p></p>
<p></p>

<p></p>







To view the full extent of my work you are more than welcome to browse through the notebook. To get a better understanding of my findings to feel free to read my blog at 
https://www.ibbysblog.com/. 

I will work on this project in the future, and try my best to make my model better by doing more feature engineering.


