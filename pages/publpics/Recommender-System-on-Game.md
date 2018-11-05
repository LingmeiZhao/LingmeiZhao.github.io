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


<img src = "/figures/RecommenderSystem/game_play_char.png" alt = "game playing bar chart">
 
<img src = "/figures/RecommenderSystem/game_purchase_char.png" alt = "game purchasing bar chart">


After analyzing the top 10 popular games, I implemented density distribution plot to see users' game playing distribution. Most users are playing game less than 100, only few users have long game-playing time. To better show the distribution, I did a log transformation of the playing time.


<img src = "/figures/RecommenderSystem/play_time_histogram.png" alt = "game playing histogram">
 
<img src = "/figures/RecommenderSystem/play_time_density.png" alt = "game playing time density">


# Data Construct
To quantify users preference for game, I used quintiles of users' game playing time, which divided all playing time into five grades as rating. Then I applied collaborative filtering to make recommendations for users using pandas and numpy. Accoding to the rating matrix, recommendate the highest rating game for users.

The collaborative filtering python code is as following:
```
import pandas as pd
import numpy as np
import matrix_factorization_utilities


df = pd.read_csv("sample_data.csv")
df1 = df[["userId", "game", "rating"]]
rating_df = pd.pivot_table(df1,
                           index ="userId",
                           columns = "game")

rating_df.to_csv("rating_matix.csv",index = False)
U,V = matrix_factorization_utilities.low_rank_matrix_factorization(rating_df.as_matrix(),
                                                                 num_features=15,
                                                                 regularization_amount=0.1)
predicted_ratings = np.matmul(U,V)

predicted_ratings_df = pd.DataFrame(index = rating_df.index,
                                    columns = rating_df.columns,
                                    data= predicted_ratings)

predicted_ratings_df.to_csv("predicted_rating.csv",index = False)

nrows, ncols = predicted_ratings.shape
users = df["userId"].unique().tolist()
games = df["game"].unique().tolist()
table = { }
for i in range(len(df)):
    (user, game) = (df["userId"].iloc[i], df["game"].iloc[i])
    table[(user, game)] = df["rating"].iloc[i]
    
for row in range(nrows):
    for col in range(ncols):
        (user, game) = (users[row], games[col])
        if (user, game) in table:
            predicted_ratings[row, col] = np.nan

max_game = [ ]
for row in range(nrows):
    gameIndex = np.argmax(predicted_ratings[row, :])
    max_game.append(games[gameIndex])

```
    


