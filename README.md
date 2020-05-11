# K<sub>pop</sub>-Nearest Neighbors

DSC160 Data Science and the Arts - Midterm Project Repository - Spring 2020

Project Team Members: 
- Chris Wynne, cwynne@ucsd.edu
- Andy Do, ando@ucsd.edu
- Saieashwar Mukund, samukund@ucsd.edu
- Matthew Widjaja, mwidjaja@ucsd.edu
- Chase Oden, coden@ucsd.edu

## Abstract

(10 points) 

For the project proposal, please write a short abstact addressing the questions below. You should replace the entire contents of this section with one to two paragraphs addressing the following:

- What is the data set that you are going to analyze?
  - We are analyzing the spotify created K-POP playlists along with other popular spotify created playlists of differing genres. 
- What is your research question? 
  - Our research question is looking into the definition of K-POP music. We believe that the genre of K-POP music is too broad to be considered only pop music, and will have a variety of ties to other genres of music. 
- What is your hypothesis about the results? 
  - Our null hypothesis is that K-pop music is different enough from other genres to be considered as its own genre
  - Our alternate hypothesis is that K-pop music is similar enough to other genres of music that it can be classified under other popular genres

- What features of the data will you use to address your question? 
  - Spotify provides simple features from audio tracks, such as tempo, time signature, duration, and key, as well as its own calculated, higher level features, such as danceability, energy, instrumentalness, and valence.
- What techniques and software tools will you use to extract these features?
  - We will be using the Spotify API to pull higher level audio features for our selected songs. Then using pandas we’ll look at combinations of various features to see how they all come together to predict the genre of a given song.
- What analytic techniques will you use?
  - We’ll do a higher level feature analysis on the features given to us by Spotify’s api. Based on these features, we will test out different classifiers to see if we can accurately distinguish between K-POP music and music of other genres to help us learn how K-POP compares to these other genres.
- What forms will your results take? (graphs, charts, images, sonification, Wordles, etc)
  - Our results will be in the form of graphs mostly comparing audio features from one genre to another. We will also attempt a classifier to group certain tracks by their metadata features, and use those to create meta-genres.
- How are you expanding on topics we have covered in class? 
  - We’re expanding on topics covered in class by combining higher level features to analyze the difference between genres as well as songs within those genres.
- Why is it interesting? (personally, culturally, politically, other)
  - We think this is really cool and culturally interesting because we hear about K-POP songs all the time but also believe that there is a large breadth of genres within the genre. We think that this is due to cultural differences between the USA and Korea which are reflected in their definition of popular music.

## Data

(10 points) 

This section will describe your data and its origins. Each item should contain a name of the data source, a link to the source, and any necessary background information such as:
- What is your cultural data source? 
  - We are pulling higher level features of songs from Spotify's API for several different genres including rock, K-pop and pop
- When was it made? 
  - While the songs themselves were uploaded to Spotify at different times, the dataset we have generated is a snapshot of what is available from Spotify as of May 6th.
- Who created the works? 
  - We included songs from various different artists across different genres however the features in our dataset were created by the Spotify team
- Is it digital native, or is it some kind of scan, recording, photo, etc., of an analog form? 
  - It is digital
- Features

| Feature          | Data Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|------------------|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| duration_ms      | int       | The duration of the track in milliseconds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| key              | int       | The estimated overall key of the track. Integers map to pitches using standard Pitch Class notation E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1.                                                                                                                                                                                                                                                                                                                               |
| mode             | int       | Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.                                                                                                                                                                                                                                                                                                                                                     |
| acousticness     | float     | A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic                                                                                                                                                                                                                                                                                                                                                                                         |
| danceability     | float     | Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable                                                                                                                                                                                                                                                                         |
| energy           | float     | Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.                                                                                                                           |
| instrumentalness | float     | Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.                                                                                                                  |
| liveness         | float     | Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live.                                                                                                                                                                                                                                                                                             |
| loudness         | float     | The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typical range between -60 and 0 db.                                                                                                                                                                                        |
| speechiness      | float     | Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.  |
| valence          | float     | A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).                                                                                                                                                                                                                                                                   |
| tempo            | float     | The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.                                                                                                                                                                                                                                                                                                                          |

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 

Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

[Spotify API Dataset Generation](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/code/cwynne_scraping.ipynb)

This notebook contains code that uses the Spotify API and the Spotipy python library to scrape a dataset of songs from multiple genres, with features being the audio features provided by Spotify. It takes in a category id (which can be thought of as a genre) and scrapes the first 50 playlists for that category, getting the audio features for all songs in each playlist. At the end, it writes the dataset to a csv. Since the scraping requires an API key, we have included our dataset as a csv in the repo under the “data/test/all/metadata/all_audio_features.csv”.

[Classification Analysis Notebook](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/code/coden_eda.ipynb)

This notebook analyzes our scraped song data and looks at the classification accuracies of every genre and K-POP as every other genre. Simply running every cell in the notebook shows two plots looking at individual genre classification error rates as well as a plot showing what genres K-POP songs can be most nearly classified as.


## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

Plots: acousticness, danceability, umap

![acousticness_graph](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/acousticness.png)

Acousticness is a prediction whether the song is acoustic or not. This is measured between a value of 0 and 1, where 0 indicates that it has very little confidence that a song is acoustic, and 1 where it has very high confidence that it is acoustic. In the boxplot kpop seems to be special, which means that there are no other genres that share a similar distribution. The boxplot that seem the most similar to kpop are pop and country, but we can see the clear difference in quartiles. However, all three of these genres have no outliers and the second quartile is more shifted towards the first quartile. We can see the similarity between pop and country, since it is on the upper half of our RandomForestClassifier.

![danceability_graph](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/danceability.png)

Danceability is a value because 0 and 1 that describes how a track is suitable for dancing. 0 being least danceable and 1 being most danceable. We can see here how the boxplot for kpop and pop are almost identical. The quartiles and whiskers are almost identical, however the outliers are only somewhat similar. We have a lot more outliers for pop and one that is very far off, whereas for kpop, we only see a few outliers and one that is not so far off. This might explain the 9.2% prediction in the RandomForestClassifier, since the quartiles tend to be very similar. Looking at the quartiles and whiskers itself, we can see that kpop is very similar to edm_dance as well, however they have very apparent different outliers. 
 
Results of Dimensionality Reduction

![umap_all](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/umap_all.png)

![umap_kpop](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/umap_kpop.png)

To be able to further understand how each of these genres compares with one another, we decided to conduct dimensionality reduction and portray our findings using UMAP with 31 nearest neighbors. The first graph shows a UMAP where the points are colored according to their genre. We see that there is a clear grouping of Classical music (blue) on the bottom left as well as a few clusters of EDM music (green) in the middle and following the points all the way to the top of the graph. To the right of these green points, there are a few clusters of pink, which represent the Pop music genre. In addition to this, we also see a lot of orange points, which represent Country music near the vertex of this parabolic graph that follow the same trend as EDM to the top of the graph. Although this graph clearly shows few clusters of certain songs, it is difficult to tell where exactly K-POP lies in all of this.

This is why we decided to do the same UMAP graph, except color the points on the binary grounds of whether or not the song is classified as K-POP or not, red being K-POP (1) and blue being other genres (0). This second graph shows red points very close to where the upward EDM trend is on the original graph, as well as a few red points where there were pink “Pop song” clusters. Lastly, there are also a few points down near the vertex of the graph, where the Country songs would be, which is something we did not expect to see. Based on these graphs and the features provided to us, K-POP can be considered most similar to these three genres, namely EDM, Pop, and Country. However, we do see many red K-POP points that follow the upward trend and that create their own clusters, showing us that K-POP is much more of its own distinct genre than many believe

Results of classifications

![classification_graph1](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/classification_graph1.png)

This first graph is our classification algorithm trained on a shuffled subset of our data, and tested on a separate shuffled test subset of the data. This shows the overall error rate across all the genres that we tested. The hardest genre to classify looks to be pop music, which has the highest error rate by over 0.4. Following pop was rock, edm, country, and hip-hop with all relatively same error rates. What we didn’t expect was to see K-POP so far down this list, as it seems our classifier was able to identify K-POP songs without much difficulty, as seen by its low error rate. This is contrary to what we thought would be the case, as we initially hypothesized that K-POP songs would have a difficult time being classified because of its wide breadth. 

![classification_graph2](https://github.com/ucsd-dsc-arts/dsc160-midterm-group-5/blob/master/results/images/classification_graph2.png)

To test what genres are closest to K-POP, we retrained our classifier on all non K-POP songs. We then tested it on only the K-POP songs. The predominant prediction was that there was no genre that fit the test set of only K-POP songs, which we believe shows that it’s a very unique genre among all the genres we tested. The next most predicted genres are pop, country, and edm, which we still found surprising. We didn’t expect Country to be in the top 3 closest genres to K-POP, yet it came in as the second most predicted genre. Pop and EDM we expected more, but overall this graph shows us that K-POP songs are distinct from other genres by a far margin.


- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

Our null hypothesis is that K-pop music is different enough from other genres to be considered as its own genre while our alternate hypothesis is that K-pop music is similar enough to other genres of music that it can be classified under other popular genres. We were unable to reject the null hypothesis as when we classified K-pop songs with our trained models, they resulted in low error rates indicating that K-pop is unique enough of a genre that it can be distinguished from other popular genres.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?
- How does your computational approach differ from the traditional art historical, musicological, manuel/subjective approach to analyzing your cultural subject? 
- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- In what future directions could you expand this work?

In today’s landscape as our society becomes more and more globally interconnected we are experiencing the largest cultural crossover in history and understanding how these cultures fit into each other is an important cultural experiment. Asian culture has been growing in popularity over the past decade and it brings new variants of Western culture such as Japanese anime and manga, Korean manhwa and Chinese manhua to name a few. The localized culture we are focusing on in our project is K-pop and how it fits into established Western genres. Although this seems like a simple question with a simple answer given the name ‘K-pop’ we would assume that it’s just pop music with Korean vocals however the answer is much much more than that as the term itself is a misnomer, a catch all term for Korean music where even rap or hip hop music from Korea is categorized as K-pop. Our project seeks to understand if K-pop truly is predominantly a genre of pop music as classified in Western culture or if overall it is more diverse than it is given credit for.

From a musicological standpoint, there is always some bias when studying music as defining genres can be extremely vague as there are a plethora of subgenres blurring the lines between different kinds of music. To that end, by approaching the study of music through a computational approach we are using computed features to define genres and by doing so remove the bias that comes from manual evaluation of music. Furthermore this computational approach allows for us to work with massive amounts of music which would not be as easy in a manual study, expanding the scope of our project which could never be reached by a more traditional approach.

Perhaps 10 or 20 years ago this research would’ve been looked down upon or confusing to a broader audience for studying a genre which at the time was niche, a fetishization of foreign culture. However, in recent years foreign culture such as K-pop has entered mainstream Western media in a large way becoming more prevalent not only on the Internet, or new media, but has managed to breach into traditional media such as K-pop groups performing and being interviewed on late night talk shows. While many people have accepted or even embraced foreign cultures, there is still an issue where certain more apprehensive individuals or those of a more traditional upbringing who are still confused by this sudden cultural shift and by being able to classify K-pop as pop music or perhaps a more diverse genre we hope to be able to bridge this gap, allowing for more harmonious interconnectivity of cultures.

In the future, by broadening our dataset and examining lower level features we could expand our project to encompass a larger portion of the musical landscape as well as improve accuracy. Furthermore, there are a multitude of other vague genres and by adjusting our project to analyze these other genres we can find how these genres fit into the traditional music labels, helping a broader audience understand them and bring them closer into the mainstream.


## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

Andy Do: Looked at all features to decide which were relevant and which were irrelevant for our models. Explained the results for the boxplot for acousticness and danceability.

Chase Oden: Helped with spotify api and spotipy data scraping. Created and tested various classification models to see relationships between K-POP music and other music genres.

Chris Wynne: Used the spotify api and spotipy to scrape the dataset and helped guide eda and classification results.

Matthew Widjaja: Processed 30-second sample of all songs in dataset, generating low level features using librosa’s mfcc then training Random Forest Classifier and KNN model on a random sample of the dataset, as training on the entire dataset takes too long, while excluding kpop songs. Afterwards predicted kpop song features on the models to see which genres are seen as most similar to the kpop genre.

Saieashwar Mukund: Performed EDA on all features scraped and helped select which features were relevant to the analysis we want by plotting each feature against one another, eliminating those with high correlations. Also conducted dimensionality reduction on features that were telling of genres and could provide clear clusters. 


## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
    - Spotipy
    - SKLearn
    - UMAP
    - Matplotlib
    - Pandas
    - Numpy
    - Json
    - Math
    - Seaborne
    - Time
    - Random
    - Urllib
    - Pydub

- Does this code require other pip packages, software, etc?
  - Spotipy, UMAP and pydub are the only other pip packages
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)
  - No

## Reference

References to any papers, techniques, repositories you used:
- https://developer.spotify.com/documentation/web-api/
- https://spotipy.readthedocs.io/en/2.12.0/

