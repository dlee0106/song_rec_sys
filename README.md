# Song Recommendation Engine (Content Based)
By: Donna Lee

## Overview 

Using a dataset (https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks) from Spotify, I looked at songs from 2000 to 2021 and their attributes (see below). There were a total of 187K songs. Each row in the dataset was a song. I wanted to create a recommendation system based on these features below given a song title and artist input. 

Attributes:

* Duration (MS)
* Danceability - how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity
* Energy - Perceptive measure of intensity and activity
* Loudness - How loud the music is
* Speechiness - Detects the presence of spoken words in a track 
* Acousticness - How acoustic a song is
* Instrumentalness - The amount of vocals in a song
* Liveness - This value describes the probability that the song was recorded with a live audience
* Valence - Musical positiveness conveyed by a track
* Tempo
* Release Date


## EDA

![pasted image 0](https://user-images.githubusercontent.com/76017120/115812570-95aa9e80-a3bf-11eb-8fbe-1fdab1430775.png)

I took a look at the correlation between our features to find if there was a problem of multicollinearity. There didn't seem to be one so I used all the features. The model ran relatively quickly with them so I didn't reduce the number of features - just subset the data by year. 

![image](https://user-images.githubusercontent.com/76017120/115812859-1f5a6c00-a3c0-11eb-818c-a83cf03fe086.png)
Taking a look at the feature means over time, we see that there is a trend towards decrease acousticness and increase energy and loudness. 

Most of the features in the dataset were already scaled so we just had to create dummy variables of the following categorical features: 

Explicit
Mode
Key
Time Signature

## Final Model
The final model calculated the Eculidean distance between the given song (user input) and the songs in the rest of the dataset. After getting all the distances, we returned the top ten for our recommendation system. 

Below is an example of our recommendations. 

## Sample Recommendations 
![image](https://user-images.githubusercontent.com/76017120/115813428-2766db80-a3c1-11eb-9b42-08d8dc87e835.png)

Try listening to these and tell us what you think. 


## Future steps

As you can see from the recommendation, some of the songs aren't in the same language as our user inputted song. For next steps, I want to create a more robust model that takes into consideration the language of the song so the engine only recommends songs in the same language. 

Another thing we could do with this is allowing for a list of songs as an input rather than just one. 







