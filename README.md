random-picker-jobber
====================
*Polymer Based Site to pick randomly attendees to a Meetup.com Event.* Inspired by the always impressive Alan Palazzolo [_who now that I type his last name I understand his gh handle_] lovingly crafted[random-picker-thingy](https://github.com/zzolo/random-picker-thingy)

###Demo
http://dev.cledwyn.com/random-picker-jobber/

###_TURNS OUT_ 
Meetup.com has a pretty rockin API.  For this case I used the Attendendance endpoint. http://www.meetup.com/meetup_api/docs/:urlname/events/:id/attendance/#list  

#Install Steps 
 1. clone git repo
 2. `bower update`
 3. rename `app-config-sample.html` to `app-config.html`
 4. replace your Meetup.com meetupSignedEventURL
 5. Done

well...

###More Details
 1. Fetch yon Meetup KEY - https://secure.meetup.com/meetup_api/key/
 2. to create your own Signed API URL, you need three things 
   1. that API Key 
   2. the "url-name" of your meetup.  (i.e. GDG-TC, NYC-GDG, AngularMN, etc) 
   3. the eventid that you wish to query.
 3. lick and stick into https://api.meetup.com/{2}/events/3/attendance?key={1}&sign=true&photo-host=public&callback=replace
 4. slam that into your favorite Chrome browser[1],  and _yoink_ out the element *x-meetup-signed-url* from the Response.  
 5. That there is your own unique signed API endpoint. [2]
   - Shoot.  One last manual futz.  You need to *remove the `&callback=replace`* [3]
   - your final url should end like `.....d2ba5f0b37e159c4b0da`


[1] I highly reccomend the extension [JSON View](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc)

[2] If you are super lazy and don't care about making your API key public, *not reccomended* then you could go with the beastie from #3.  Your call.  Just sayin'. *YOU WILL* still need to remove the `&callback=replace` off the end.

[3] the polymer JSONP object will append it's onwn callback parameter variable
