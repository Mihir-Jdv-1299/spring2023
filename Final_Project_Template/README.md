# DATA ANALYSIS AND VISUALIZATION OF YOUTUBE VIDEO METRICS AND TITLES

Authors:   

- **Mihir Ravindra Jadhav** 
- **Poorva Bhatia**
- **Pushkar Shirish Kulkarni**
- **Ankita Anand**

YouTube Video:  [Final Project Video Presentation](https://youtu.be/foRi8DH0vBU)

---

## Task List

| ID | TASK DESCRIPTION | DUE DATE | STATUS |
| --- | --- | --- | --- |
| 1. | Research and study the YouTube API documentation | April 19 | COMPLETED |
| 2. | Setup YouTube API credentials and authorize requests | April 21 | COMPLETED |
| 3. | Searching and writing Python code to call the YouTube API and retrieve video metadata and metrics with appropriate referencing | May 01 | COMPLETED |
| 4. | Cleaning and preprocessing dataset using Pandas library | May 07 | COMPLETED |
| 5. | Perform exploratory data analysis and generate insights | May 12 | COMPLETED |
| 6. | Create data visualizations using data visualization libraries and generate corresponding line charts, bar charts, histograms, etc. to analyze different matrices such as view count, like and dislike count, for a particular YouTube channel | May 13 | COMPLETED |
| 7. | Write final project report of findings which will include project objectives, data analysis, methodology and conclusions | May 15 | COMPLETED |
| 8. | Record, edit and upload YouTube video showcasing project | May 15 | COMPLETED |
| 9. | Commit final changes to the README.md file in GitHub Repository | May 16 | COMPLETED |
| 10. | Check for final changes and submit the entire project with all the necessary documentation and referencing | May 17 | COMPLETED |

---

## Introduction

- *The purpose of our project -*

	- The purpose of our YouTube API project is to leverage the power of YouTube's API and Python's pandas and data visualization libraries to analyze and visualize video metrics. 
	
	- By accessing YouTube's API, we can retrieve data such as views, likes, dislikes and other relevant statistics for videos on YouTube channels.
	
	- Our project aims to gain valuable insights into video performance, engagement, and audience behavior by exploring and analyzing the data provided by the YouTube API. 
	
	- We will utilize Python's pandas library to analyze, filter, and process the retrieved data, allowing us to perform various data manipulations and calculations.

- *The type of data we are using -*

	In our YouTube API project, we are using data retrieved from the YouTube API to perform analysis and visualization of video metrics. The YouTube API provides access to various types of data related to YouTube videos, channels, and audience engagement. Here are the types of data we are utilizing:

 1. Video Data:
	- We gather data about individual videos, including information such as video titles, descriptions, upload dates, durations, and thumbnail images.
	
	- We retrieve metrics such as view counts, like counts, and dislike counts to understand the performance and popularity of videos.

 2. Channel Data:
	- We collect data about YouTube channels, including channel names, descriptions, subscriber counts, and channel creation dates.

	- We analyze metrics like total video counts, average views per video, and engagement rates to assess the overall performance and success of channels.

 3. Engagement Data:

	- We access data related to viewer engagement, such as views, likes and dislikes.

	- We analyze the engagement metrics to measure the level of interaction and feedback from viewers, helping us understand audience sentiment and preferences.

- *What are we doing with this data?*

	- With the processed data, we will employ Python's data visualization libraries, including matplotlib and seaborn, to create meaningful visualizations such as bar plots, scatter plots, and more. 

	- These visualizations will help us uncover patterns, trends, and relationships within the video metrics data, enabling us to draw informative conclusions about the performance of YouTube videos.

	- By presenting our findings through intuitive and visually appealing graphs and charts, our project aims to provide a comprehensive understanding of the video statistics and metrics available through the YouTube API. 

	- This analysis can assist content creators, marketers, and YouTube channel owners in making data-driven decisions regarding content strategy, audience engagement, and video optimization.


- *What types of analysis are conducting?*

 1. Video Metrics Analysis:
	- We analyze video metrics such as views, likes, and dislikes to understand the popularity and engagement levels of YouTube videos.
	
	- We calculate metrics like average views per video, like-to-dislike ratios, title sentiment analysis, and engagement rates to measure the overall success and reception of the videos.

 2. Performance Trends Analysis:
	- We examine the trends and patterns in video metrics over time to identify any significant changes or growth.
	
	- We plot line charts or area charts to visualize how views, likes, or other metrics evolve over a specific period, helping us identify periods of high or low performance.

 3. Channel Comparison Analysis:
	- We compare the performance of different YouTube channels by analyzing their video metrics side by side.
	
	- We create bar plots or stacked bar charts to showcase the comparative performance of channels in terms of views, likes, and other metrics.

---

## References

- [YouTube API](https://developers.google.com/youtube/v3/docs)

---

## Requirements

- *Python Packages/Libraries* -

	- The following are the packages/libraries we have used in our analysis:

1. Pandas.
2. Seaborn.
3. Matplotlib.
4. Collections.
5. Wordcloud.

To install these packages, type the following commands in either a terminal window or command prompt window:

```
pip3 install pandas
pip3 install seaborn
pip3 install matplotlib
pip3 install wordcloud
```

Once the packages have been installed, its installation can be verified by opening a Python interactive shell by typing "**python3**" in either a terminal window or command prompt window.

```
import pandas
import seaborn
import matplotlib
import collections
import wordcloud
```

Import each package one by one to ensure there are no import errors. If there are no errors, it implies the packages have been successfully installed.

- *API keys*

To install and set up API keys, the process varies depending on the specific API the user intends to use. Since, we have used the **YouTube API** for our project, here is the link to create one for the user:

[YouTube API Key](https://console.cloud.google.com/)

1. Create or select a project:
	-  Click on the project dropdown menu at the top of the page, then click "New Project". Enter a name for your project and click "Create".

2. Enable the YouTube API:
	- Once the user has a project, ensure that it is selected in the project dropdown menu.
	- Click on the "Navigation menu" (☰) in the upper-left corner of the console.
	- Scroll down and click on "APIs & Services" and then "Library".
	- In the search bar, type "YouTube" and select "YouTube Data API v3" from the results.
	- Click on the "Enable" button to enable the YouTube Data API for a project.

3. Create API credentials:
	- After enabling the API, go back to the "APIs & Services" menu.
	- Click on "Credentials".
	- On the Credentials page, click on the "Create Credentials" button and select "API key" from the dropdown menu.
	- A dialog box will appear displaying your API key. You can copy it to your clipboard by clicking the "Copy" button.

4. Restrict your API key (recommended):
	- To enhance the security of your API key, it's recommended to set restrictions.
	- Click on the "Restrict key" button next to your API key.
	- Configure the restrictions according to your needs. The user can specify IP addresses, websites, or API usage quotas to control how your key can be used.
	- Click "Save" to apply the restrictions to your API key.

It is extremely crucial to keep the API key secure and avoid exposing it publicly. The user can then use this API key to authenticate and make requests to the YouTube API in Python code or applications.

---

## Explanation of the Code

- First we install/ load the necessary libraries that we would be requiring for the project like Pandas for data analysis, seaborne and matplotlib for data visualization.

```
from googleapiclient.discovery import build
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
from textblob import TextBlob
import wordcloud
```

- The code below initializes the YouTube API by importing the necessary modules and setting the API key. It also defines a list of channel IDs.

- In this project we will be analyzing popular infometric channels and understanding how the title of video is important for the video's success.

```
api_key = 'AIzaSyCFXejJxu7xbdw6ovsxf92kaZwSGDWo1VQ'

channel_ids = ['UCcyq283he07B7_KUX07mmtA', # Business Insider
               'UC4rlAVgAK0SGk-yTfe48Qpw', # Bright side
               'UCgNg3vwj3xt7QOrcIDaHdFg', # Polymatter
               'UCsXVk37bltHxD1rDPwtNM8Q', # Kurzgesagt – In a Nutshell
               'UC4QZ_LsYcvcq7qOsOhpAX4A'  # Cold Fusion
              ]

youtube = build('youtube', 'v3', developerKey=api_key)
```

- __Function to get channel statistics__

Now we define a code which makes a request to the YouTube API to retrieve channel statistics, including snippet, content details, and statistics for the specified channels.

```
def get_channel_stats(youtube, channel_ids):
    all_data = []
    request = youtube.channels().list(
                part='snippet,contentDetails,statistics',
                id=','.join(channel_ids))
    response = request.execute() 
    return response

#get_channel_stats(youtube, channel_ids)
```

We write another function that retrieves channel specific information like Channel name, Subscriber count, Views, Total videos and playlist ID.

```
def get_channel_stats(youtube, channel_ids):
    all_data = []
    request = youtube.channels().list(
                part='snippet,contentDetails,statistics',
                id=','.join(channel_ids))
    response = request.execute() 
    
    for i in range(len(response['items'])):
        data = dict(Channel_name = response['items'][i]['snippet']['title'],
                    Subscribers = response['items'][i]['statistics']['subscriberCount'],
                    Views = response['items'][i]['statistics']['viewCount'],
                    Total_videos = response['items'][i]['statistics']['videoCount'],
                    playlist_id = response['items'][i]['contentDetails']['relatedPlaylists']['uploads'])
        all_data.append(data)
    
    return all_data
```

Function call that returns a list od dictionaries that gives the required information.

```
get_channel_stats(youtube, channel_ids)

 [{'Channel_name': 'Insider Business',
  'Subscribers': '7750000',
  'Views': '3883058990',
  'Total_videos': '5611',
  'playlist_id': 'UUcyq283he07B7_KUX07mmtA'},
 {'Channel_name': 'PolyMatter',
  'Subscribers': '1830000',
  'Views': '203411607',
  'Total_videos': '138',
  'playlist_id': 'UUgNg3vwj3xt7QOrcIDaHdFg'},
 {'Channel_name': 'ColdFusion',
  'Subscribers': '4490000',
  'Views': '424881006',
  'Total_videos': '458',
  'playlist_id': 'UU4QZ_LsYcvcq7qOsOhpAX4A'},
 {'Channel_name': 'Kurzgesagt – In a Nutshell',
  'Subscribers': '20500000',
  'Views': '2306144306',
  'Total_videos': '179',
  'playlist_id': 'UUsXVk37bltHxD1rDPwtNM8Q'},
 {'Channel_name': 'BRIGHT SIDE',
  'Subscribers': '44500000',
  'Views': '10654312661',
  'Total_videos': '5838',
  'playlist_id': 'UU4rlAVgAK0SGk-yTfe48Qpw'}]
```

The above list is then loaded into a datafram called channel_data for data visualization.

```
channel_statistics = get_channel_stats(youtube, channel_ids)
channel_data = pd.DataFrame(channel_statistics)
channel_data
```

Now, the following graph shows a comparitive statistic - Subscriber count.

```
# Converting Subscribers, Views and Total_videos to numeric  
channel_data['Subscribers'] = pd.to_numeric(channel_data['Subscribers'])
channel_data['Views'] = pd.to_numeric(channel_data['Views'])
channel_data['Total_videos'] = pd.to_numeric(channel_data['Total_videos'])
channel_data.dtypes

sns.set(rc={'figure.figsize':(10,8)})
ax = sns.barplot(x='Channel_name', y='Subscribers', data=channel_data)
```

![Subs_ChannelName](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/b37e368f-19a9-4188-882e-753d75ed5ab8)

From the graph we can see that "BRIGHT SIDE" has highest number of subscriber at 44.5 million while ploymatter has less than half a million subscriber.

The code below compares the channels based on the total views it gets.

```
ax = sns.barplot(x='Channel_name', y='Views', data=channel_data)
```

From the graph we can notice that "Insider Business" desipite having fewer subscribers when compared to Kurzgesagt generated higher total views.

The code below compares the channels based on their total views.

```
ax = sns.barplot(x='Channel_name', y='Total_videos', data=channel_data)
```

![Unknown-2](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/f8d7b540-5435-4497-898d-51b41cabc77e)

An interesting observation that can be derived form this graph is that both "BRIGHT SIDE" and "Insider Business" have uploaded the same number of videos but "BRIGHT SIDE" has significantly higher total views and subscriber count.

- Function to get video ids -

Using one of the channel names we store the playlist_id in a variablw using which we will extract all the video_ids of the videos uploaded by the channel.

```
playlist_id = channel_data.loc[channel_data['Channel_name']=='ColdFusion', 'playlist_id'].iloc[0]
```

This codedefines a function that retrieves the video IDs of the videos in the specified playlist.

```
def get_video_ids(youtube, playlist_id):
    
    request = youtube.playlistItems().list(
                part='contentDetails',
                playlistId = playlist_id,
                maxResults = 50)
    response = request.execute()
    
    video_ids = []
    
    for i in range(len(response['items'])):
        video_ids.append(response['items'][i]['contentDetails']['videoId'])
        
    next_page_token = response.get('nextPageToken')
    more_pages = True
    
    while more_pages:
        if next_page_token is None:
            more_pages = False
        else:
            request = youtube.playlistItems().list(
                        part='contentDetails',
                        playlistId = playlist_id,
                        maxResults = 50,
                        pageToken = next_page_token)
            response = request.execute()
    
            for i in range(len(response['items'])):
                video_ids.append(response['items'][i]['contentDetails']['videoId'])
            
            next_page_token = response.get('nextPageToken')
        
    return video_ids
```

A function call is made to store all the video_ids in variable using which video specific information is retrieved.

```
video_ids = get_video_ids(youtube, playlist_id)
```

- Function to get video details - 

The get_video_details function takes the youtube object (initialized YouTube API) and a list of video_ids as input. It retrieves the details and statistics of the specified videos.

```
def get_video_details(youtube, video_ids):
    all_video_stats = []
    
    for i in range(0, len(video_ids), 50):
        request = youtube.videos().list(
                    part='snippet,statistics',
                    id=','.join(video_ids[i:i+50]))
        response = request.execute()
        
        for video in response['items']:
            video_stats = dict(Title = video['snippet']['title'],
                               Published_date = video['snippet']['publishedAt'],
                               Views = video['statistics']['viewCount'],
                               Likes = video['statistics']['likeCount'])
#                               Comments = video['statistics']['commentCount'])
            all_video_stats.append(video_stats)
    
    return all_video_stats
```

All the information is then stored in a datafrome called Video_data.

```
video_details = get_video_details(youtube, video_ids)
video_data = pd.DataFrame(video_details)
```
Some of the column are converted to appropriate datatype for visualization.

```
video_data['Published_date'] = pd.to_datetime(video_data['Published_date']).dt.date
video_data['Views'] = pd.to_numeric(video_data['Views'])
video_data['Likes'] = pd.to_numeric(video_data['Likes'])
video_data['Views'] = pd.to_numeric(video_data['Views'])
video_data
```

To get the sentiment of the title The getPolarity function takes a text parameter(Title in our case), calculates the polarity using TextBlob, and returns the polarity score (ranging from -1 to 1) of the text.
We also convert the 'Published_date' column in the video_data DataFrame to datetime format using the pd.to_datetime() and extract the year using functions from pandas.

```
#Functions to get the subjectivity and polarity
def getPolarity(text):
    return  TextBlob(text).sentiment.polarity  #between -1 and 1

#Adding polarity columns
video_data['Polarity'] = video_data['Title'].apply(getPolarity)


# Extract the year and create a new 'year' column
video_data['Published_date'] = pd.to_datetime(video_data['Published_date'])
video_data['year'] = video_data['Published_date'].dt.year

video_data
```

The plot below groups the total views and aggregates it aat a year level. This shows us the trentd in annual views recieved by the channel year-on-year.

```
# Group by year and calculate the sum of 'value' column
grouped_df = video_data.groupby('year')['Views'].sum().reset_index()

# Plot a bar graph
sns.barplot(x='year', y='Views', data=grouped_df)
plt.xlabel('Year')
plt.ylabel('Sum of Views')
plt.title('Sum of Views by Year')

# Display the plot
plt.show()
```

![Unknown-3](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/59aa744c-1f8c-4397-b2ba-d6512e501233)

It would also be beneficial if we analyze the total number of video the channel uploades in a year. To get that we group by the occurances of a year and aggregate it.

```
# Group by year and count the occurrences
year_counts = video_data.groupby('year').size().reset_index(name='count')

# Plot a bar graph using Seaborn
sns.barplot(x='year', y='count', data=year_counts)
plt.xlabel('Year')
plt.ylabel('Count')
plt.title('Number of Occurrences per Year')
plt.show()
```

The code snippet provided defines a function called contains_capitalized_word and performs returns true if the Title has capitalized word on a DataFrame. It also generates a pie chart using the matplotlib.pyplot library.

![Unknown-4](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/412db63b-5ae4-4b6f-a13a-89f8a7dcc3a4)

```
def contains_capitalized_word(s):
    for w in s.split():
        if w.isupper():
            return True
    return False


video_data["contains_capitalized"] = video_data["Title"].apply(contains_capitalized_word)

value_counts = video_data["contains_capitalized"].value_counts().to_dict()
fig, ax = plt.subplots()
_ = ax.pie([value_counts[False], value_counts[True]], labels=['No', 'Yes'], 
           colors=['#003f5c', '#ffa600'], textprops={'color': '#040204'}, startangle=45)
_ = ax.axis('equal')
_ = ax.set_title('Title Contains Capitalized Word?')
```

![Unknown-5](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/758fcf00-e12e-440e-9519-8ad678b6938b)

We also analyze what the lenght of the title is and it it has any bearing on the views a video gets. We first see what the distribution of the title lenght is.

```
video_data["title_length"] = video_data["Title"].apply(lambda x: len(x))

fig, ax = plt.subplots()
_ = sns.distplot(video_data["title_length"], kde=False, rug=False, 
                  hist_kws={'alpha': 1}, ax=ax)
_ = ax.set(xlabel="Title Length", ylabel="No. of videos", xticks=range(0, 110, 10))
```

![Unknown-6](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/f82c2bc1-c9dd-42d0-b3f5-e258d07bbdd4)

This scatter plot shows the relation between title length and the views a view gets.

```
fig, ax = plt.subplots()
_ = ax.scatter(x=video_data['Views'], y=video_data['title_length'], color= 'red', edgecolors="#000000", linewidths=0.5)
_ = ax.set(xlabel="Views", ylabel="Title Length")
```

![Unknown-7](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/6f69c5bb-dd41-4118-a414-4b0353d4652e)

- Now let's see how the dataset variables are correlated with each other: for example, we would like to see how views and likes are correlated, meaning do views and likes increase and decrease together (positive correlation)? Does one of them increase when the other decrease and vice versa (negative correlation)? Or are they not correlated?

- Correlation is represented as a value between -1 and +1 where +1 denotes the highest positive correlation, -1 denotes the highest negative correlation, and 0 denotes that there is no correlation.

Let's see the correlation table between our dataset variables (numerical and boolean variables only)

```
video_data.corr()
```

Now let's visualize the correlation table above using a heatmap.

```
h_labels = [x.replace('_', ' ').title() for x in 
            list(video_data.select_dtypes(include=['number', 'bool']).columns.values)]

fig, ax = plt.subplots(figsize=(10,6))
_ = sns.heatmap(video_data.corr(), annot=True, xticklabels=h_labels, yticklabels=h_labels, cmap=sns.cubehelix_palette(as_cmap=True), ax=ax)
```

![Unknown-8](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/126d4acd-ddff-485a-816f-59b03c6d7863)

Let's see if there are some words that are used significantly in video titles. We will display the 25 most common words in all of video titles.

```
title_words = list(video_data["Title"].apply(lambda x: x.split()))
title_words = [x for y in title_words for x in y]
Counter(title_words).most_common(25)
```

```
[('The', 116),
 ('-', 77),
 ('How', 60),
 ('of', 52),
 ('is', 49),
 ('the', 44),
 ('Note', 39),
 ('|', 38),
 ('and', 36),
 ('Galaxy', 36),
 ('to', 35),
 ('A', 26),
 ('Samsung', 24),
 ('ColdFusion', 22),
 ('a', 21),
 ('BIG', 21),
 ('Story', 19),
 ('Android', 18),
 ('Why', 17),
 ('in', 17),
 ('HTC', 16),
 ('From', 15),
 ('You', 14),
 ('A.I.', 14),
 ('Are', 14)]
 ```
 
Let's draw a word cloud for the titles of our videos, which is a way to visualize most common words in the titles; the more common the word is, the bigger its font size is.
 
 ```
 wc = wordcloud.WordCloud(width=1200, height=500, 
                         collocations=False, background_color="white", 
                         colormap="tab20b").generate(" ".join(title_words))
plt.figure(figsize=(15,10))
plt.imshow(wc, interpolation='bilinear')
_ = plt.axis("off")
```
---

## How to Run the Code

1. Ensure that you have registered for the YouTube API key.

2. Ensure that you have installed necessary Python packages.

3. Open a terminal window or a command prompt window.

4. Open the python file **(Youtube_Analysis.ipynb)** in a python environment like Anaconda, jupyter notebook to run the codes individually.

5. Run all the codes in sequence to ensure the data is loaded in the variables.

---

## Results and Conclusion

- The title is often the first thing viewers see when they come across a video. 

- A compelling and attention-grabbing title can entice viewers to click and watch the video. It should be concise, descriptive, and engaging to pique the interest of potential viewers. 

- The title has a significant impact on the video's click-through rate. When a video appears in search results or related videos sections, an appealing title can entice users to click on the video over others. 

- A high CTR indicates that the title successfully captures the interest of viewers, driving more traffic to the video.

- Hence from our analysis we have figured out for a specified channel what words are frequently used and the relation between the length of the title with the views it gets. This can help the youtuber form titles that are captivating and can attract viewer’s attention.

![Unknown-9](https://github.com/IE-555/final-project-Mihir-Jdv-1299/assets/124175956/8f67dcd1-2826-496b-98e9-8cb1629b2a6c)

- The thing that worked well was that we extracted data from the api and analyzed it well. 

- We could have incorporated additional details that can embellish the current analysis. Things like viewer demographic and behavior can be added on to this analysis so that the youtuber has additional information to work with.

---

## Future Scope

1. Audience Analysis -
	
	- We can analyze the demographic information provided by YouTube API, such as age, gender, and geographic location of the viewers, to gain insights into the target audience.

	- We can also create pie charts, bar plots, or heatmaps to visualize the distribution of viewers across different demographics, helping us understand the audience composition.

2. Engagement Analysis - 

	- We could analyze the engagement level of viewers through metrics like comments, likes, and shares to gauge the level of interaction with the videos.

	- We might also perform sentiment analysis on comments to understand the overall sentiment and feedback of viewers.

3. Video Category Analysis -

	- We can explore the video categories or tags associated with the videos to identify popular content areas and analyze their performance.

	- We coudl also create bar plots or word clouds to visualize the distribution of video categories or identify frequently used tags.

---
