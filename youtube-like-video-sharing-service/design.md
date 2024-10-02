# Youtube like Video Sharing Service

Only features we are focusing for this is users' ability to upload videos from anywhere and play them from anywhere at scale.

## Actual Youtube Loads
 - 720,000 hours of videos uploaded every day ~ 0.7Mill hours uploaded every day
 - This means 4.3 petabytes of storage every day
 - Youtube stores every video in multiple resolutions and bitrates for efficient streaming
 - Youtube also stores multiple copies for redundancy

## For our design, we will use Approximate loads
 - Let us start with 1 million users
 - 10% users upload 1 video per week - 100K videos/week ~ 20K videos / day -  upload times can be slightly slow and be batched with delayed update to user
 - 30% users play 10 videos a day - 3 million videos / day = ~100K videos/hour = ~2K videos / min = ~400 videos / sec   //approx calcs 
 - Storage needs - MASSIVE -
 -   Every year, we get 100K * 52 = ~5 million new videos. Each video takes max 1GB let us say => 5 million GB = 5000TB additional storage every year in just one instance
 -   Do we need CDNs for fast streaming across the globe?

## Basic components
 > An API to upload videos -  scaled web servers with distributed storage at the back
 > A notification service to send notification to users that video uploaded successfully/failed
 > A way for users to search for a video based on tags and find it
 > What kind of technology would be needed for streaming videos??? 
