1. Follow users
2. create tweets (chr limit 140 chrs)
3. view feed (only from the users we follow)

500M Users
200M Active Users

20B read/day

Size of a tweet - 1MB * 20 B == 20PB of data

50M tweets per day

Read heavy, write less

Certain users have more followers, how to handle them

Relational DB
Object Storage for images.

CDN ---- Object storage

Pull based algorithm


API

createTweet(uid,text,media)
getFeed(uid)

uid should be passed in the http header.

follow(uid,followid)

Tweets Table -- tweet id, user id, timestamp, text, media reference
Follow Table -- Followee, follower. Index on follower

Tweets table:
Read only replicas 
Sharding based on uid while writing
on reading, it should hit multiple shards to get tweets of the followees

Cache might reduce latency

To reduce latency more,

while creating a tweet it goes to pub/sub as well in addition to DB, a cluster to process the feeds and creates a feed cache 

