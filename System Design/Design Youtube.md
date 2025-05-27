1. watch videos
2. upload videos
3. recomendation
4. search videos
5. comments, likes, views count 

read is heavy and write is less

100 watches : 1 uploads

Reliability - once uploaded, the videos should not be deleted or corrupted

Availability > Consistency 

Reduce latency 

object storage for storing videos
noSQL DB for storing metadata

MongoDB:
JSON object, collection of documents, no joins needs, data is denormalised
user collection
video collection

if someone changes profile pic, it will be handled async 

API

upload(title,desc,video,channel)

After object storage it sends to queue and encoded and stored again

For Viewing:

CDN --- object storage encoded 
cache to store metadata - LRU

live streaming - UDP
movies and other stuff - TCP

