## Project Title
### We-Rate-Dogs (Twitter Data Analysis)

## Project Description
### WeRateDogs Enhanced Twitter Archive contains data extracted from 2356 of the 5000+ tweets from the @dog_rate twitter account. The WeRateDogs is a twitter account that rate people’s dogs with comments about those dogs.
### We used Python for this project because it has built-in features to apply this wrangling method to this data set to achieve the analytical goal
### There were challenges like missing data, incorrect data types, and duplicate data. These were solved by removing missing data, changing incorrect data types to correct data types and dropping duplicate values.

## How To Use The Project
#### Download and read the We Rate Dogs Twitter Archive into a dataframe 
##### twitter_archive = pd.read_csv('twitter-archive-enhanced.csv')
##### twitter_archive.head()


#### Use the Requests library to download the tweet image prediction (image_predictions.tsv)
####  download and read the tweet image predictions file


##### url =  'https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv'
##### response = requests.get(url)


#### Open a file to handle the content of the url
##### with open(url.split('/')[-1], mode = 'wb') as file:
   ##### file.write(response.content)


#### response


#### Read the downloaded tweet_json file line by line
##### with open('tweet_json.txt', 'r') as file:
#####    for line in file:
 #####       lines = file.readlines()
 

#### Converting incorrect timestamp to correct datetime data type
##### twitter_archive_clean['timestamp'] = pd.to_datetime(twitter_archive_clean.timestamp)


#### Removing tweets with missing data expanded_url
##### twitter_archive_clean = twitter_archive_clean[twitter_archive_clean.expanded_urls.notnull()]


#### Dropping duplicate data
##### image_predictions_clean = image_predictions_clean.drop_duplicates(['jpg_url'])


