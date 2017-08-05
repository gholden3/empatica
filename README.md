# empatica
Dashboard for showing real-time visualizations of your app downloads. 

Since I don't have real app download data (open to suggestions for better data streams!), 
the app currently uses Twitter location data to fake it. I've implemented a real-time listener 
connected to the Twitter stream API, using Python's Tweepy library. 

Tweets are then published to a Kafka Topic. 

Storm Spout consumes tweets from Kafka Topic, and emits tuples to be processed by Storm Bolt. 

Storm Bolt processes and analyzes tweets. 

Analyzed results are sent to a DynamoDB table. 

Flask webapp can retrieve results from DynamoDB table. 
