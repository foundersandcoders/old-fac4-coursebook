
###STEP 1

If streaming: Connect to the Twitter API using a streaming connection. Listen for events of data being emitted in the form of tweets to founders and coders that also contain one of the relevant hashtags. 

If using the REST API: create a request to the Twitter API that is triggered every <time-interval tbc> to retrieve relevant tweets.



###STEP 2

When we query the Twitter API, it will return the tweet results as objects.

The key information we want to extract and save for later is:

text-body: string
hashtag: #stop/#go/#continue
num-retweets: number
original tweeter: string
voters : array
Twitter will give us the whole tweet as one string. Therefore, in order to separate out the text body from the hashtags, we will use regex.

Number of retweets, original tweeter and voters (i.e. the retweeters) are provided in the object Twitter gives us, so are simpler to access.

A key job is to distinguish between new tweets and retweets. When there is a new tweet, we want to create a new object to store that suggestion in, whereas if there is a retweet, we want to update an existing suggestion object with an increased retweet count, and the user name of the person who retweeted will be added to the list of tweeters or 'voters' of the original tweet.
Luckily, the structure of retweets is different to tweets.
The property 'retweeted_status' only exists for retweets. So we can use an 'if' statement with this property and separate the two.
Within retweet objects, there is a property 'retweet-count'. This is what we will use to increase tell how many votes a suggestion gets.

if (retweeted_status exists) {
	fetch the retweet-count
};
else (retweeted_status doesn't exist ){
	create new object
};

We can also check the ID of the tweeter to make sure the same person has not tweeted the same text in order to cheat the voting system.


###STEP 3

In order to access the data properties of the JSON object we will .stringify it.

We will have to use string manipulation with regular expressions to sort out of the tweeted text e.g. remove "@founderscoders".

We will write it to the filesystem in the form of a JSON object as a series of name: value pairs. Each tweet will be written as a new file. 

There will either be a timestamp on each tweet or each file will be written in an order that easily allows whoever is reading the filesystem to easily identify which tweets are most recent and which they have already received the data from. The filename should also contain the id number of the tweet so we can easily find the right file to update if we have a retweet. 


```
{ created_at: 'Tue Feb 24 12:24:51 +0000 2015',
  id: 570197663351746560,
  id_str: '570197663351746561',
  text: 'RT @RorySedgwick: @founderscoders testing #STOP',
  source: '<a href="http://twitter.com" rel="nofollow">Twitter Web Client</a>',

  user: 
   { id: 1613170598,
     id_str: '1613170598',
     name: 'Greg Aubert',
     screen_name: 'gregaubs',
     location: 'London',
     url: 'http://gregaubert.com/',
     description: 'New Entrepreneurs Foundation 2014   |   Travel, tourism & startups',
     protected: false,
     verified: false,
     followers_count: 80,
     friends_count: 65,
     listed_count: 9,
     favourites_count: 1,
     statuses_count: 84,
     created_at: 'Mon Jul 22 16:21:53 +0000 2013',
     utc_offset: null,
     time_zone: null,
     geo_enabled: false,
     lang: 'en-gb',
     contributors_enabled: false,
     is_translator: false,
     profile_background_color: '676B67',
     profile_background_image_url: 'http://pbs.twimg.com/profile_background_images/378800000032343247/a7cbb5fd198fc0794589b73c75e91251.jpeg',
     profile_background_image_url_https: 'https://pbs.twimg.com/profile_background_images/378800000032343247/a7cbb5fd198fc0794589b73c75e91251.jpeg',
     profile_background_tile: false,
     profile_link_color: '6595A3',
     profile_sidebar_border_color: 'FFFFFF',
     profile_sidebar_fill_color: 'DDEEF6',
     profile_text_color: '333333',
     profile_use_background_image: false,
     profile_image_url: 'http://pbs.twimg.com/profile_images/378800000171420897/763c79ed2ed13af097ca4e7bf382430e_normal.jpeg',
     profile_image_url_https: 'https://pbs.twimg.com/profile_images/378800000171420897/763c79ed2ed13af097ca4e7bf382430e_normal.jpeg',
     default_profile: false,
     default_profile_image: false,
     following: null,
     follow_request_sent: null,
     notifications: null },
  geo: null,
  coordinates: null,
  place: null,
  contributors: null,

  
  retweeted_status: 
   { created_at: 'Tue Feb 24 12:19:48 +0000 2015',
     id: 570196391567466500,
     id_str: '570196391567466496',
     text: '@founderscoders testing #STOP',
     source: '<a href="http://twitter.com" rel="nofollow">Twitter Web Client</a>',
     truncated: false,
     in_reply_to_status_id: null,
     in_reply_to_status_id_str: null,
     in_reply_to_user_id: 971846516,
     in_reply_to_user_id_str: '971846516',
     in_reply_to_screen_name: 'founderscoders',
     user: 
      { id: 2447724711,
        id_str: '2447724711',
        name: 'Rory Sedgwick',
        screen_name: 'RorySedgwick',
        location: 'London',
        url: null,
        description: null,
        protected: false,
        verified: false,
        followers_count: 15,
        friends_count: 62,
        listed_count: 1,
        favourites_count: 1,
        statuses_count: 21,
        created_at: 'Sun Mar 30 18:23:45 +0000 2014',
        utc_offset: null,
        time_zone: null,
        geo_enabled: false,
        lang: 'en',
        contributors_enabled: false,
        is_translator: false,
        profile_background_color: '000000',
        profile_background_image_url: 'http://abs.twimg.com/images/themes/theme1/bg.png',
        profile_background_image_url_https: 'https://abs.twimg.com/images/themes/theme1/bg.png',
        profile_background_tile: false,
        profile_link_color: '4A913C',
        profile_sidebar_border_color: '000000',
        profile_sidebar_fill_color: '000000',
        profile_text_color: '000000',
        profile_use_background_image: false,
        profile_image_url: 'http://pbs.twimg.com/profile_images/511502370375618560/bVwVBWH2_normal.jpeg',
        profile_image_url_https: 'https://pbs.twimg.com/profile_images/511502370375618560/bVwVBWH2_normal.jpeg',
        default_profile: false,
        default_profile_image: false,
        following: null,
        follow_request_sent: null,
        notifications: null },
     geo: null,
     coordinates: null,
     place: null,
     contributors: null,
     retweet_count: 1,
     favorite_count: 0,
     entities: 
      { hashtags: [Object],
        trends: [],
        urls: [],
        user_mentions: [Object],
        symbols: [] },
     favorited: false,
     retweeted: false,
     possibly_sensitive: false,
     filter_level: 'low',
     lang: 'en' },


  retweet_count: 0,
  favorite_count: 0,
  entities: 
   { hashtags: [ [Object] ],
     trends: [],
     urls: [],
     user_mentions: [ [Object], [Object] ],
     symbols: [] },
  favorited: false,
  retweeted: false,
  possibly_sensitive: false,
  filter_level: 'low',
  lang: 'en',
  timestamp_ms: '1424780691360' }
```
