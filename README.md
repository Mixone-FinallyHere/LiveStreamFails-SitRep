# LiveStreamFails-SitRep
SitRep for the attempted phshing and baiting done by the user WallaceSauce through their OVH deployment against a series of streamers.

## What happened ?
The scammer/baiter whom is likely known as WallaceSauce (username to keep under watch potentially) maintained a MySQL database on the OVH hosting platform. On this database they uploaded some 340 records of streamer names with images and profile pics associated, as well as some optional data for them to play different messages in their baiting link. Small note, the user is not very smart, they had various issues with OVH and left critical data open easily as well as open communications on port 22. This is what is usually called a "dumb idea".

They used some very basic javascript and php to get the IP of conenction and show it to user. This info is not as sensitive as most people will lead you to beleive, any website you visit has your IP, its not ideal to show everyone but the amount of damage that can be done is relatively limited as long as you maintain a healthy and secure way of connecting to the internet and using your devices.

The technical thing it does is simply has an invisible "block" in the HTML (source code) of the site that after a small delay displayed a horrific picture and played a specifc song/noise.

### Why was the streamer name relevant?
The way the baiter coded this, a piece of php code was looking at a thing called URL parameters, that means those things begind the url such as `URL/?article=USERNAME`. This allowed thier code to simply look up in their database via a separate files called `check.php` and `func.php` and generate a page that had images and logos and profile pics of the streamer name in question in the URL making it look like a "genuine" article for the first couple of seconds.

## Was I affected ?
The list of users that were "attacked" can be found in the file [Names.txt](https://github.com/Mixone-FinallyHere/LiveStreamFails-SitRep/blob/main/Names.txt), you can quickly just use `Cntrl+F` or look through the names to find yourself.

The file [Affected.json](https://github.com/Mixone-FinallyHere/LiveStreamFails-SitRep/blob/main/Affected.json) shows an actual data extract from their database. The data format is as follows:
```json
{
    "id" : "ID Number",
    "streamerName" : "STREAMER_NAME",
    "linkStr" : "STREAMER_NAME_FOR_URL",
    "delay" : "TIME_TO_WAIT",
    "weave" : "RELATED_TO_BAITING",
    "sound" : "SOUND_TO_PLAY",
    "waffle" : "PIC_TO_DISPLAY",
    "streamerPic" : "PIC_OF_STREAMER",
    "facial" : "HAVENT_FIGURED_OUT_WHAT_THIS_ONE_IS_FOR"
}
```

If you have any questions feel free to reach out to me on discord at Mixone#7740
