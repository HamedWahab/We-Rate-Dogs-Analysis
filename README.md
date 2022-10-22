# We-Rate-Dogs-Analysis
## Introduction
The dataset that would be wrangled (and analyzed and visualized) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage. WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017.

This file (image_predictions.tsv) is present in each tweet according to a neural network. It is hosted on Udacity's servers and would be downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv

Gathering each tweet's retweet count and favorite ("like") count at the minimum and any additional interesting data. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. 

## Assessing Data
After assessing the data, the following quality and tidiness issues were discovered:
### Quality issues
- The in_reply_to_status, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp columns have empty values.
- Drop unnecessary columns
- The datatype of the 'tweet_id' is in integer, and should be converted to string (for all the three data)
- The source text is embedded in the source url.
- The timestamp is in object datatype, and should be converted to datetime.
- The rating numerator and denominator column have some wrong values.
- Some of the names 'none', 'a', 'an', 'this' etc. are not dog names.
- The dog breeds columns (p1, p2 and p3) have inconsistent case sensitivies.
### Tidiness issues
- The dogger, floofer, pupper and puppo columns should all be under one column as it represents only one variable (dog stage).
- Merge the archive data, df_image and df_json into one master data dataset.
## Analyzing Data
After cleaning and careful analysis of the data, few insights were deduced:
- Although a lot of dog names are unknown. Charlie, Lucy, Cooper, Oliver seems to be the most common dog names.
- Pupper has the highest frequency amongst the dog stages.
- Majority of the tweets were sent via iPhone while minority were sent via Web then TweetDeck.



