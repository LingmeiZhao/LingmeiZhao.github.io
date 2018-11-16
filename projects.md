---
layout: default
---

## Projects

##### Steam Game Recommender System
I did simple statistics discribing. After delete few extram data, I plotted two bar charts about users' game playing time and users' game purchasing to analyzed the top ten popular games. From the bar charts, we can see the popular played games are also purchased most.

<img src = "/figures/recommenderSystem/game_play_char.png" alt = "game playing bar chart" width="500">

<img src = "/figures/recommenderSystem/game_purchase_char.png" alt = "game purchasing bar chart" width="500">

I implemented density distribution plot to see users' game playing distribution. Most users are playing game less than 100, only few users have long game-playing time. To better show the distribution, I did a log transformation of the playing time.
 
<img src = "/figures/recommenderSystem/play_time_histogram.png" alt = "game playing histogram" width="500">

<img src = "/figures/recommenderSystem/play_time_density.png" alt = "game playing time density" width="500">

To quantify users preference for game, I used quintiles of users' game playing time, which divided all playing time into five grades as rating. Then I applied collaborative filtering to make recommendations for users using pandas and numpy. Accoding to the rating matrix, recommendate the highest rating game for users.

##### Sentiment Analysis on Hotel Reviews
I did a independent project of analyzing about 35912 hotel reviews, which was downloaded from Kaggle. This data set is perfect for sentiment analysis because it has users' ratings for hotels, that reprent users' sentiment bias. According to the ratings, I can divided every reviews in train data set into positive and negative.

I plotted a bar chart to analyze the top ten states in USA with most hotel reviews. In addition, I used a words cloud about hotel marks, which can reflet hotels' types in the dataset.

<img src = "/figures/HotelReview/hotelReviews_province.jpg" alt = "Characters Occurrence" width="500">
<br>
<img src = "/figures/HotelReview/wordCloud.jpg" alt = "Characters Occurrence" width="500">
<br>
<img src = "/figures/HotelReview/reviewsCloud.jpg" alt = "Characters Occurrence" width="500">

I needed to select important words as fetures to train my model. Therefore, I used Chi-squre  test to select important words. Meanwhile, I caculated the frenquency of every words. The fetures should have big chi-squre value and high frequency. Based on this rule, I select about 1000 words as fetures.

Next, I trained my model using Logistic Regression. Finally, using the trainning result to get the test result, and compare with the real reault.

The confuse matrix graph:
<img src = "/figures/HotelReview/Normal Confusion Matrix.jpg" alt = "Characters Occurrence" width="500">
The total precise is about 63%. The model has better performance on positive review.

[back](./)
