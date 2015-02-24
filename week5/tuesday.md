# Tuesday: Jigsaw Classroom

## The project: Build a *Stop Go Continue* dashboard. 

1. A user tweets to @founderscoders a suggestion with the hashtag *#stop*, *#go* or *#continue*
1. Other users can retweet a suggestion to vote on it;
1. Users should be able to go to a dashboard and see one or more visualisations of all the votes for all the suggestions

### The project is going to be broken down into four parts:

1. A node client to pull all relevent tweets and stores the relevent data from each tweet in a file as a JSON object;
1. A node server that responds to requests by reading the file and sends it as a JSON response;
1. A web page that polls the server for data at intervals and updates the page when the data changes;
1. A dashboard that shows incoming votes for different suggestions.
