---
layout: post
title: Raffi Krikorian - How to use Geolocation in your web app
categories:
- Other
tags:
- Twitter
- Geolocation
- Raffi Krikorian
- FOWA
---
<p>Last Friday I attended the <a href="http://futureofwebapps.com/dublin-2010/">Future of Web Apps</a> conference in Dublin.  It was an excellent experience (everything was better than last year bar the atmosphere) and I wanted to write up a few of the things I have learned from it.  Taking each talk in the order they were given I will write up a little blurb about them.</p>
<p>The first talk was by <a href="http://twitter.com">Twitter</a>'s <a href="http://twitter.com/raffi">Raffi Kirkorian</a>, he is the lead developer of the Twitter geospatial APIs.  I felt he delivered his content well and I enjoyed the presentation a lot.</p>
<p>I have done no work involving Geolocation, but from what Raffi was saying there is a lot of potential that can be unlocked without too much effort on the developers part.</p>
<p>He first of all gave a definition of location which is context plus relevancy, which was interesting for me because I had never really thought of location as anything other than a little bit of extra meta data for refining searches and categorising content.</p>
<p>We learned that with geolocation things like tweets and articles can become globally applicable but locally relevant.  Basically this means that whilst information such as "Belfast airport is closed due to ash clouds today" is globally applicable it is really only relevant to people who live in or wanted to travel to Belfast.</p>
<p>One of the examples used in the presentation was <a href="http://yaketee.com/">yaketee.com</a>, this is a chat service based on location.  In my personal opinion the site serves only as a proof of concept because there are more effective ways to talk to people in your local community without going online and remembering a fairly odd sounding URL!  That being said it is an excellent proof of concept, very slick and with some excellent fallback measures.  You should check it out.</p>
<p>One of the issues raised by the talk was that when considering location we have to remember that people have different names for different things, an example given was language barrier where Rome and Roma are the same place.  I am guessing that from this we could also give the example of different groups of people referring to the same thing in different ways even in the same language, for example Lavery's Bar is better known to the locals as Lav's (or to some as just shite!).</p>
<p>Two examples given which would allow you to combat this are to use geolocation tables in the form of either <acronym title="Where On Earth Indentifier">WOEID</acronym> and <acronym title="Twitter GeoID">TwID</acronym>.</p>
<p>Where On Earth Identifier is stable and language agnostic.</p>
<p>Twitter geoID is simple at the moment but getting better.</p>
<p>These can be accessed by passing in your longitude and latitude into the tables and getting back a unique code for that one place on earth.</p>
<p>Different ways were discussed to get someones location from their web browser, the two I have notes for are IP-Based location which is dead easy, is server side but not really that local so only useful for area/country and W3C Geolocation which is done in JavaScript and works in most internet browsers.</p>
<p>The last example of the day was <a href="ttp://fireeagle.yahoo.net/">fireeagle.yahoo.net</a> this is a pretty cool service for updating your location around the web from one easy to use place.</p>
<p>To sum up, this was a really useful talk about something I had very little exposure to.  There are already people doing some really cool stuff with Geolocation but I think we have only scratched the surface.  Cheers to Raffi for giving it!</p>
