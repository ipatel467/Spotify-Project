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




Another feature we will be going over today is Loudness. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Let's take a look at the Loudness Distribution below. 


![Screen Shot 2021-01-19 at 10 34 07 AM](https://user-images.githubusercontent.com/52756457/105064744-bcfd7280-5a42-11eb-8717-3526f60c19ab.png)

We can see that this histogram is skewed to the left, unlike the others. This means that there are more songs containing a higher loudness than songs with lower loudness. I wonder why this may be the case. I am assuming because younger people like louder music which could possibly be a contributing factor.



One feature I decided to look at the Time Signature. The time signature is a notational convention to specify how many beats are in each bar (or measure). I wanted to see which time signature had the highest song popularity. Looking at the bar chart below we can see that 3 beats per measure(Time Signature) has the highest average popularity. 

![Screen Shot 2021-01-19 at 10 34 46 AM](https://user-images.githubusercontent.com/52756457/105064829-d4d4f680-5a42-11eb-8786-f52400bc75c6.png)


Even though, 3 beats per minute(Time Signature) had the highest average popularity I still felt the need to investigate further. This time I took the approach of getting the total popularity sum of all songs. This led me to find something very interesting. We can see that 4 beats per minute are the 2nd highest in terms of popularity by looking at the averages. But we get something very different when we look at the total sum. 

We can see that 4 beats per minute are significantly greater than all the other different beats per measure. This will call for even further investigation. Could this be due to there being too many songs that have 4 beats per measure? Or could it be due to the songs in the 4 beats per measure bin having a very high popularity score? I will have to search up more on this and examine the findings.


Another feature we decided to look into was the "Key" feature. The Key is the estimated overall key of the song. This is a measure that uses standard pitch notation. Standard pitch notation is a method of specifying musical pitch by combining a musical note name and a number identifying the pitch's octave. I decided to see the average popularity of a song by Key. Below is a bar chart containing the results.

![Screen Shot 2021-01-19 at 10 35 34 AM](https://user-images.githubusercontent.com/52756457/105064890-e5856c80-5a42-11eb-97b1-e896aa967af7.png)

We can see that the Keys with the highest average popularity are 2,3, and 10. But once again I am not satisfied with just looking at the averages. I decided to dig a little deeper and see the total sum by popularity.

![Screen Shot 2021-01-19 at 10 53 16 AM](https://user-images.githubusercontent.com/52756457/105066572-8de80080-5a44-11eb-84c3-3d494f5d9aee.png)

Once again I am interested to see that Key 1 has the highest popularity sum while key 3 has the lowest popularity sum. We can also see that key 2 has been moved down the ranks in terms of popularity by sum. Key 2 had the 2nd highest mean for popularity, but key 2 has the 2nd lowest popularity sum. Once again this could be due to an imbalance of songs ranging in popularity. We will have to investigate some more to find our solution.

### Modeling <a name="modeling"></a>

![Alt Text](https://media.giphy.com/media/1zi2FQvx8c6jXZB9dm/giphy.gif)



### Results <a name="results"></a>

These are my first round models also referred to as "Vanilla Models". These models are used to establish a baseline for this project, and we will continue to improve them as time goes on. Let's see how well these models performed. 


Below are the results of my linear regression model.  We can see that we got a R_squared of 0.177. This is low R_squared, and we definitely want to work on improving it, but what does this mean? This means that model is capturing less than 18% of the data needed to predict a song's popularity. However, this is completely fine because it is only our first round model.


![Screen Shot 2021-01-19 at 10 43 54 AM](https://user-images.githubusercontent.com/52756457/105065405-70fefd80-5a43-11eb-895b-32f358ecc7da.png)

Another model I created was one using an XGBoost algorithm. Overall, this model performed a little bit better than the linear regression model. We can see that we got a R_squared of 0.260. The XGBoost model is capturing around a quarter of the data needed to predict a song's popularity. This is still somewhat of a low R_squared, but we will definitely see improvements as we gather more data, preprocess it, and conduct feature engineering. 

![Screen Shot 2021-01-19 at 10 44 01 AM](https://user-images.githubusercontent.com/52756457/105065363-680e2c00-5a43-11eb-8f7e-2a9fe4de44f2.png)
 
 
 Below are the results to my AdaBoost "Vanilla" model. Overall this model yielded the best results in comparison to the other two. Once again if we look at the R_squared we can see that we got a value of 0.510. The AdaBoost model is capturing 51% of the data needed to predict a song's popularity. I am actually very happy to see these results in comparison to the other models. However, we will continue to improve all our models with feature engineering and hyperparameter tuning in the near future.  
 

![Screen Shot 2021-01-19 at 10 44 09 AM](https://user-images.githubusercontent.com/52756457/105065452-7e1bec80-5a43-11eb-9079-42730db1361b.png)
 
 
 

<p>My second best performing model was the Gradient Boosting model. The Gradient Boosting model has a R_Squared of 0.527. This means this model is capturing almost 53% of the data needed to predict a song's popularity. This model performed slightly better than the XGBoost.</p>


<p>
<img width="732" alt="Screen Shot 2020-12-16 at 11 48 44 AM" src="https://user-images.githubusercontent.com/52756457/102387227-ba1be780-3f95-11eb-84b4-fd719bc27583.png">
</p>


<p>Last but not least, below is the code for the AdaBoost model. This was the best performing model in comparison to all the other models. This AdaBoost model gave me a R_squared of 0.612 which once again means this model is gathering 61% of the data needed to predict a song's popularity. </p>



<p>
<img width="729" alt="Screen Shot 2020-12-16 at 11 48 25 AM" src="https://user-images.githubusercontent.com/52756457/102387146-a2dcfa00-3f95-11eb-92ff-a00337d8c3de.png">
</p>


I was able to improve my metrics by using feature engineering. I plan on coming back to this project with more data and more technique to imporve the metrics of the model. 



To view the full extent of my work you are more than welcome to browse through the notebook. To get a better understanding of my findings to feel free to read my blog at 
https://www.ibbysblog.com/. 

I will work on this project in the future, and try my best to make my model better by doing more feature engineering.


