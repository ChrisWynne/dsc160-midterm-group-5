# Project Title

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
  - Our hypothesis is that K-POP music will correlate to other popular genres. We think this is because there’s a wide breadth of K-POP genres classified under the generic K-POP genre. 
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
  We are pulling higher level features of songs from Spotify's API for several different genres including rock, K-pop and pop
- When was it made? 
  While the songs themselves were uploaded to Spotify at different times, the dataset we have generated is a snapshot of what is available from Spotify as of May 6th.
- Who created the works? 
  We included songs from various different artists across different genres however the features in our dataset were created by the Spotify team
- Is it digital native, or is it some kind of scan, recording, photo, etc., of an analog form? 
  It is digital

## Code

(20 points)

This section will link to the various code for your project (stored within this repository). Your code should be executable on datahub, should we choose to replicate your result. This includes code for: 

- data acquisition/scraping
- cleaning
- analysis
- generating results. 

Link each of your notebooks or .py files within this section, and provide a brief explanation of what the code does. Reading this section we should have a sense of how to run your code.

## Results

(30 points) 

This section will contain links to documentation of your results. This can include figures, sound files, videos, bitmaps, as appropriate to your domain of analysis. Each result should include a brief textual description, and all should be listed below: 

- image files (`.jpg`, `.png` or whatever else is appropriate)
- audio files (`.wav`, `.mp3`)
- written text as `.pdf`

## Discussion

(30 points, three to five paragraphs)

The first paragraph should be a short summary describing your results.

The subsequent paragraphs could address questions including:
- Why is this culturally relevant?
- How does your computational approach differ from the traditional art historical, musicological, manuel/subjective approach to analyzing your cultural subject? 
- How do you think the original artists/musicians would respond to this type of analysis? Would it change/inform their practice in some way?
- How do your results relate to broader social, cultural, economic political, etc., issues? 
- In what future directions could you expand this work?

## Team Roles

Provide an account of individual members and their efforts/contributions to the specific tasks you accomplished.

## Technical Notes and Dependencies

Any implementation details or notes we need to repeat your work. 
- Additional libraries you are using for this project
- Does this code require other pip packages, software, etc?
- Does this code need to run on some other (non-datahub) platform? (CoLab, etc.)
  No

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
