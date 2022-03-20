# Twitter_Page_WeRateDogs_Insights

## Overview

Real-world data rarely comes clean. Using Python and its libraries, I gathered data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. I documented wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and SQL.

## Used_skills
### Python3 / Pandas / Tweepy / Seaborn / JSON

## A glance on the data 

[twitter-archive-enhanced.csv](https://github.com/Ahmedhassan139/Twitter_WeRateDogs_Insights/files/8310349/twitter-archive-enhanced.csv)

[tweet-json.txt](https://github.com/Ahmedhassan139/Twitter_WeRateDogs_Insights/files/8310350/tweet-json.txt)

[archived_breeds_favs_retweets_final.csv](https://github.com/Ahmedhassan139/Twitter_WeRateDogs_Insights/files/8310351/archived_breeds_favs_retweets_final.csv)
#### JSON data from twitter API

## Wrangling Process Report 

### Gathering:

- I imported twitter-archive-enhanced.csv, by pandas.
- Imported image-predictions.tsv by requests library then created path using os library.
- Collected data from tweet-json.txt without tweeter developer account, then created panda data frame and saved as favs_tweets_data.

### Assessing and Cleaning:

Pliminary visual assessing for the csv files done by excel file and Pandas.

#### Tidiniess and missing data:

##### Twitter_archive_enhanced:
o dogs classifications (doggo, puppo, etc....) are distributed over three columns while it should be in one column using melt that gives value observation which is done under the name dog classification.
o Dropped columns like (retweeted_status_id,retweeted_status_user_id,retweeted_stat us_timestamp), are not complete(empty), removed as they don’t add value.
##### Image_prediction:
o columns of p1, p2, p3 and p1dog,..etc related to pics prediction were reformatted to have two columns one for the breed type and other for confidence, the reformatting done by for loops based on priorities for p1 = True if not then p2=True if not, then p3 = True otherwise the prediction is failed then concatenated all together.
o The resulted two columns of prediction diverted to Dataframe then merged with twitter_archive_enhanced under name archived_breeds_clean.

##### favs_tweets_data:
o tweets and favorite counts merged with archived_breeds_cleanforming archived_breeds_favs_retweets final dataframe which I used for quality assessing and cleaning.
### Quality:
- missing some names (745 of none values), replaced None with nan.
- Ratings numerators out of range for the rating_numerator as max is **1776**, neglected all values bigger than **20**, I took the numerator as a scale over ten.
- timestamp type is not correct, converted to to_datetime type to be accessible.
- tweet_id should be string , converted using as type.
- Removed duplicated tweet_id .
- columns of p1, p2, p3 and p1dog,..etc need to be more discriptive (already done in tidiness).
- Dropping non predicted breeds and replacing them with failed prediction.

### Final DataFrame was stored as archived_breeds_favs_retweets_final.csv and conducted visualization and analysis programatically by python library.

## Report of the Insights

### Insights and Analysis
we rate dogs is a twitter account where dog lovers post ratings about different dog breeds in a funny way giving them different ratings with domenators base 10,Data here provided from __-_- to ---- and hereby some quick facts about activities done on we rate dogs account.
• During the period from 2015 till August, 2017, tweets of dogs were maximum in 2016, 1183 tweet.
• Average tweets per month is 196, and the most month when people make tweets regarding dogs is December, while the month with fewest tweets is August.
• The most retweeted post was related to the dog breed 'Labrador_retriever' and it was retweeted 79515.0 times.
<img width="486" alt="Screen Shot 2022-03-20 at 2 16 07 AM" src="https://user-images.githubusercontent.com/54185918/159142731-b197f4e0-d758-4bfb-9d0e-2ee67cf0313a.png">
### The most retweeted dog ‘Labrador_retriever'

Common rating_numerators over on base 10 is 12 after neglecting any value above 20.

<img width="497" alt="Screen Shot 2022-03-20 at 2 17 49 AM" src="https://user-images.githubusercontent.com/54185918/159142764-b4135ef2-b238-4251-a143-d712e1346805.png">


The top 5 breeds of dogs tweeted is golden_retriever as in the figure below , but we notice that 'Labrador_retriever' the most retweeted dog comes No. 2nd still popular!, and then Pembroke and then chihuahua, and number five is Pug.

<img width="628" alt="Screen Shot 2022-03-20 at 2 19 52 AM" src="https://user-images.githubusercontent.com/54185918/159142807-199527cf-10e3-477b-877e-64e96842a9aa.png">

## How the code works in Jupyter notebook ?


https://user-images.githubusercontent.com/54185918/159142991-058e6ba3-03c0-4dd1-9041-85af1362bc9a.mp4


