# Twitter WeRateDogs
## About Data
WeRateDogs is a Twitter account that rates dogs with humorous comments and rating being a denominator of 10 most of the time and its numerator is always greater than the denominator, twitter users/dog_owners also tend to state the dog stage in which their dogs belong, either doggo, floofer, pupper or puppo. These are just <a href="https://zippypaws.com/blog/doggolingo-101-internet-language-of-the-dogs/">doggolingo</a>
- doggo is an affectionate name for a dog
- floofer is a big ol’ (big old) doggo with an abundance of fluffy fur
- pupper is a smol(small) doggo or a puppy.

From this account with so many tweets and retweets about dogs one would like to know which breed of dogs is mainly owned by people and which dog tend to be the "cutest", knowing the cutest might be from the number of favorite count or the retweeted count but most times people do not always favorite or retweet a tweet because they like it, it might just be to view at a later time or they actually do find it very ridiculous and want others to see but in this study we will assume the favorite count or retweet is because users/viewers actually like what they see. 

## Analysis Process
**Must have**
* <a href="https://numpy.org/">numpy</a>
* <a href="https://pandas.pydata.org/">pandas</a>
* <a href="https://matplotlib.org/">matplotlib</a>
* <a href="https://pypi.org/project/requests/">requests</a>
* <a href="https://www.programiz.com/python-programming/json">json</a>
### Data Source
The files used are support materials from Udacity
* <a href="https://video.udacity-data.com/topher/2018/November/5bf60c1e_twitter-archive-enhanced-2/twitter-archive-enhanced-2.csv">Twitter-archive-enhanced</a>
* Image-predictions hosted on Udacity's servers and should be downloaded programmatically using the `Requests` library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv
* <a href="https://video.udacity-data.com/topher/2018/November/5be5fb7d_tweet-json/tweet-json.txt">Tweet-json</a> 
used are support materials from Udacity.
## Data Assesing and Cleaning
Assesing individual dataframes brought about quality and tidiness issues

**Quality**
 `twitter_archive` table: 
* in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id and expanded_urls have null values (NaN)
* timestamp should not be an object data type, it should be datetime
* the columns doggo, floofer, pupper and puppo should be values not column names
* source column should show the exact source of tweet instead of the url
* tweet_id, retweeted_status_id, retweeted_status_user_id, in_reply_to_status_id, in_reply_to_user_id in float should be a string datatype
* duplicated rating because of retweets

 `twitter_image` table: 
* p1, p2, p3 sometimes in uppercase and names separated by underscore(_)
* twitter id should be a string not an int
* duplicated values in jpg_url column

 `tweet_df` table:
* column name id should be tweet_id as in `twitter_archive` and `twitter_image` table for easy merge

**Tidiness**

* the `twitter_image` table have tweets that are not dogs
* timestamp column should be split into date and time columns
* the three tables should be merged to one
* using neural network classified with more than one type of breed

## Summary of Findings
The Golden Retriever among the different 113 breeds is common amidst Twitter users but the breed with the highest rating is the Clumber and the least common is the Scotch Terrier but the Japanese Spaniel has a very low rating

The analysis also shows that most dogs are in their pupper stage.
