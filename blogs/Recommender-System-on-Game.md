---
layout: default
---

Recommender System is essential in E-commerce. I am very interested in the recommender system. Hence I created a game recommender system based on the dataset provided by steam.

### Data Visualization

To identify outliers in the dataset, I carried out exploratory analysis on it. After I removed anomalies, I plotted two bar charts regarding users’ games' play time and purchase records to analyze the top ten favorite games. From the bar charts, we can see the popular games in the scale of play time are also got the most purchases.


<img src = "/figures/recommenderSystem/game_play_char.png" alt = "game playing bar chart" style="width:400px;height:300px;">


<img src = "/figures/recommenderSystem/game_purchase_char.png" alt = "game purchasing bar chart" style="width:400px;height:300px;">

After analyzing the top 10 popular games, I plotted the distribution of users’ games' play time. Most users are playing a game less than 100 hours, while a few users have longer game-playing time. To better show the distribution, I made a log transformation of the playing time.
 
<img src = "/figures/recommenderSystem/play_time_histogram.png" alt = "game playing histogram" style="width:400px;height:300px;">

<img src = "/figures/recommenderSystem/play_time_density.png" alt = "game playing time density" style="width:400px;height:300px;">


### Collaborative Filtering
To quantify users preference for the games, I used quantiles of users’ game playing time, which divided all playing time into five grades as a rating. Then I applied collaborative filtering to make recommendations for users using pandas and numpy. According to the rating matrix, the program can recommend the highest score game for users.
