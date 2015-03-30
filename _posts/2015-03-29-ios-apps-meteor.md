---
layout: post
status: publish
published: true
title: Creating an iOS application in 5 minutes using Meteor.
author:
  display_name: Toby
  email: toby.osbourn@googlemail.com
categories:
- Developer Help
tags:
- Meteor
---

[Meteor](https://www.meteor.com) is a great framework for making applications that need a persistent back end. Using Meteor I have been able to get projects in front of clients way sooner than I normally would and I have been able to get prototypes of my own projects out for feedback without spending too much time architecting the back end.

In fact I even made [an app in an hour and pushed it to production](/making-app-just-hour-meteor-heroku/).

So Lets Make An app!

First things first we need to install Meteor – If you are using OSx or any flavour of Linux you should be fine to use the following command


```
curl https://install.meteor.com/ | sh
```

Now we want to create a new app;

    meteor create cool_app
    cd cool_app
    meteor

With these three commands we have created a new application, moved into it and started the meteor server.

The demo application is pretty standard, it has a button that you can click and a counter increments. This doesn’t really show off how quick it is to get persistence within Meteor, so lets fix this by changing two lines and adding one inside of `cool_app.js`

Add this to the top of the file; 

```
Clicks = new Mongo.Collection(“clicks”);
```

Replace the Session get with;

```
Clicks.find({}).count();
```

And replace the Session set line with;

```
Clicks.insert({});
```

Ok now this is cool, now we can have live updating of our data when people come to the site AND it is persisted. All for free.

You can test this by opening multiple browser windows and watching the click count go up.

This is nice but the subject of my post mentions iOS applications.

Assuming you are using OSx you are about 2 minutes away from having your new application running on the iPhone simulator that comes with xCode.

    meteor install-sdk iOS
    meteor add-platform iOS
    meteor run iOS

Now you can use your application natively and you will see that your session running in the browser will effect that iPhone app and vice versa.
