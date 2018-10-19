---
layout: post
title: Recommender System on Game
category:
- Data Science
- Recommender System
- Recommender System
--- 

Recommender System is very import in business and Internt. I am very interested in recommender system, so I found a game dataset and I did a game recommender system based on the dataset.

# Data Visualation

This dataset is rather clean. Therefore, I did not spend much time to clean data. However, to find whether there exist extram data, I did simple statistics discribing. After delete few extram data, I plotted two bar charts about users' game playing time and users' game purchasing to analyzed the top ten popular games. From the bar charts, we can see the popular played games are also purchased most.

<table class="wide">
<tr>
  <td class="left">
    <a
        <img src = "/figures/RecommenderSystem/game_play_char.png" alt = "game playing bar chart">
    </a>
  </td>
  <td class="right">
    <a 
        <img src = "/figures/RecommenderSystem/game_purchase_char.png" alt = "game purchasing bar chart">
    </a>
  </td>
</tr>
</table>

After analyzing the top 10 popular games, I implemented density distribution plot to see users' game playing distribution. Most users are playing game less than 100, only few users have long game-playing time. To better show the distribution, I did a log transformation of the playing time.

<table class="wide">
<tr>
  <td class="left">
    <a
        <img src = "/figures/RecommenderSystem/play_time_histogram.png" alt = "game playing histogram">
    </a>
  </td>
  <td class="right">
    <a 
        <img src = "/figures/RecommenderSystem/play_time_density.png" alt = "game playing time density">
    </a>
  </td>
</tr>
</table>

# Data Construct
To quantify users preference for game, I used quintiles of users' game playing time, which divided all playing time into five grades as rating. Then I applied collaborative filtering to make recommendations for users using pandas and numpy. Accoding to the rating matrix, recommendate the highest rating game for users.


