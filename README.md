# Final Project: The Billboard Equation (Available at https://monicahong.shinyapps.io/The-Billboard-Equation/)

![Music banner](./imgs/music.jpg)

## Music as a Domain: An Introduction

### Why are we interested in this domain?

>_“Music is a language that doesn’t speak in particular words. It speaks in emotions, and if it’s in the bones, it’s in the bones.”_  
― Keith Richards, Singer and Songwriter for the Rolling Stones

According to [Dr. Michelle Millis Chapel](https://michellechappel.com/), a former University of California psychology professor who later turned to a career in music, scientists have discovered [fifteen mental and emotional benefits](https://www.lifehack.org/317747/scientists-find-15-amazing-benefits-listening-music) (and counting) of listening to music. Spanning from stress relief to elevated physical and mental performance across several metrics, the benefits of such an easily accessible commodity are endless. It's no wonder that we make it such a big part of our lives, plugging it in whenever we need a pick-me-up. Music makes us feel **good**.

Yet not all music is created equal, and listeners everywhere carefully cater their playlists to personal preferences. As passionate Spotify users with a shared love for music, our group hopes to use data and information to better understand how songs distinguish themselves and rise to the top within such a competitive space. Tired of trying to distance ourselves from the "overplayed" and the "overrated", we instead wish to explain the bits and pieces that bring a song to such a coveted status. In doing so, we hope that we might unearth insights that can speak to our psyche, helping us to better understand how music exploits various facets of the human condition.

### What are other examples of data driven projects related to this domain?

Using a subset of the free-to-use Million Song Dataset (MSD) available online, as made available online by the UCI Machine Learning team, Kaggle user Vinay Shanbhag built a [model](https://www.kaggle.com/vinayshanbhag/predict-release-timeframe-from-audio-features) for predicting a song's release year based on features within the music. His project was based upon the underlying theory that music has evolved significantly with time, changing in its nature with every generation.

Using data collected from the National Endowment of the Arts, the Bureau of Labor Statistics, and the U.S. Bureau of Economic Analysis, online real-estate broker Movoto developed an [interactive map](https://www.spin.com/2014/04/interactive-all-american-music-map-by-genre/) depicting American music tastes by state. This project can be helpful in gaining a better understanding of demographic differences by geography, since different areas are shown to prefer different types of music.

Using data scraped directly off of its own web API, Spotify's team created [Spotify.me](https://spotify.me/en) in order to give its users insight as to their listening habits. Leveraging the data they collect from running their product, Spotify also launched Spotify for Brands, which uses data from its users in order to help businesses conduct analyses on consumer behavior and patterns. This is a great example of how data can be used to satisfy simple curiosity, since everyone is (at least to some degree) interested in knowing more about themselves.

### What data-driven questions does our project aim to answer?

Since our project revolves around the idea of "popularity" in the world of music, our biggest question we hope to answer is: **_Which characteristic of a song is the best predictor of the song's popularity?_** We could answer this by conducting a regression analysis for all combinations of popularity and a song feature, and then comparing their R-square values against one another.

From that, we hope to then broaden our scope and answer along the same vein: **_How does each of the individual observable characteristics affect a song's popularity?_** Looking at the coefficient from the regression analyses, we could determine each individual characteristic's effect on the song's popularity.

Finally, we would like to deviate slightly from the focus on popularity, by evaluating the relationship between different song characteristics that might somehow influence one another. For instance, a question of this nature might be: **_How does tempo affect the danceability of a song?_** To check for relationships such as this one, we could just run an analysis comparing two factors outside of popularity, plotting them against one another. For instance, in this case, we would plot the tempo (in beats per minute) of the song against its danceability rating.

Branching out from there, of course, there are countless tangential questions that can be answered through analysis of our data. For instance:
- **_By how much does an artist's popularity inflate the popularity of his or her songs?_**
- **_Are certain words in song-titles correlated to higher popularity?_**
- **_If we were to create our own song, what would be our formula?_**

Overall, we hope that the answers to our questions will give us a better idea of _how_ music appeals to our minds.

## Data: Origins and Explanations

### Where did our data come from?

We downloaded our data from Kaggle, an online community of data scientists and machine learners hosted by Google. The data was in .csv form, collected by Kaggle user Tomigelo. More information about Tomigelo is provided further down below. The [Kaggle page](https://www.kaggle.com/tomigelo/spotify-audio-features#SpotifyAudioFeaturesApril2019.csv) from which the dataset was downloaded has two separate files, but we downloaded the more recent one for the sake of completeness in the track list.

### How was our data generated or collected?

The data was generated and made available through the official [Spotify Web API](https://developer.spotify.com/documentation/web-api/), offered through Spotify For Developers. Tomigelo then collected the data from the API using [Spotipy](https://spotipy.readthedocs.io/en/latest/).

>"Spotipy is a lightweight Python library for the Spotify Web API. With Spotipy you get full access to all of the music data provided by the Spotify platform."  - Official Spotipy Docs

The extended details of Tomigelo's data collection process are listed in his [GitHub](https://github.com/tgel0/spotify-data/blob/master/notebooks/SpotifyDataRetrieval.ipynb).

### Who collected our data?

Our data was collected by [Tomigelo](https://www.kaggle.com/tomigelo), a Kaggle user based in Germany. Tomigelo is a gold-level contributor to Kaggle discussion boards, as well as a bronze-medal contributor to kernels and a contender in machine learning competitions.

### What or who is our data about?

Our data is about the audio features and popularity ratings of 130,663 different Spotify tracks. These tracks are collected from the period **up to April of 2019**, as can be seen through the release dates of the songs listed. The data included reflects data spanning all users of Spotify worldwide.

### How many observations (rows) does our data entail?

The dataset contains **130,663** different observations (rows); each row is for a different Spotify track.

### How many features (columns) are captured by our data?

Our data captures **17** different features:
- **Artist name** (e.g. Snow Patrol)
- **Track ID** (e.g. 2RM4jf1Xa9zPgMGRDiht8O)
- **Track name** (e.g. Heal Me)
- **Acousticness** (0-1 scale of whether the track is acoustic)
- **Danceability** (0-1 scale of how suitable a track is for dancing)
- **Duration** (In milliseconds)
- **Energy** (0-1 scale of perceptual intensity and activity)
- **Instrumentalness** (0-1 scale representing instrumental : vocal ratio)
- **Key** (e.g. 0 = C, 1 = C#, 2 = D, etc.)
- **Liveness** (0-1 scale of audience presence)
- **Loudness** (-60 to 0 decibels measure of loudness)
- **Mode** (0 = Minor, 1 = Major)
- **Speechiness** (0-1 scale of presence of words in a track)
- **Tempo** (beats per minute)
- **Time Signature** (Beats in each measure)
- **Valence** (0-1 scale of the positivity of a track)
- **Popularity** (0-100 scale of a song's popularity)

### What questions from above can we answer using our data?

By using a regression analysis, we can use our data to determine **the correlation between each individual characteristic and the song's popularity**. To demonstrate this to the user, we can use an individual scatterplot for each song characteristic as the x-axis, setting the y-axis in each as the song's popularity.

From looking at all of the scatterplots together, our data will then help us narrow down **which of the characteristics is the main driver behind the song's popularity**. By creating an additional plot and table for a multiple regression analysis of the data, we will be able to confirm the best predictor for song popularity, which would answer our main question.

Then, by using a scatterplot matrix comparing different song characteristics against one another, we can determine the **relationship between variables such as tempo and danceability**. Since almost all of the columns have been listed in continuous numeric terms, the scatterplot matrix would be appropriate for finding most of the relationships possible.

By looking at the data collected from over 130,000 tracks in the past, we might even lay the groundwork for predicting new songs' rise to fame in the future. By looking at the relationships between these seventeen different  song features, we'll be the ones telling you tomorrow, **"I liked New Town Road before it was cool."**

Visit us at our site: https://monicahong.shinyapps.io/The-Billboard-Equation/
