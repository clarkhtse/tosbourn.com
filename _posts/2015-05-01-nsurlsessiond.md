---
layout: post
title: Speeding up the internet on OSx Yosemite
categories:
- OSx
tags:
- 
---

The internet in my part of London is pretty dire and I have to do everything I can to make sure that any bandwidth I use is done so carefully so that I can fully enjoy the internet and the benefits it has.

I wanted to spend some time looking at the `Activity Monitor` to see if there were any apps that were constantly phoning home or trying to deliver large payloads of data.

Something that kept on coming up again and again was a process started by my user called `nsurlsessiond`

Before I go into what it is and why I turned it off I want to share a quick before and after shot of packets in / packets out.

![Packets In and Out before and after nsurlsessiond was stopped](/img/nsurlsessiond.jpg)

I am sure you can see the time I decided to kill it!

## nsurlsessiond

nsurlsessiond is the process that is used by iCloud to sync your iCloud Drive/Photos/Contacts/etc between your machine(s) and the iCloud server.

I don’t use iCloud Drive for anything, nor do I use Photos, even so this process was constantly sending packets home to Apple.

I decided to go into my iCloud settings and turn off both iCloud Drive and Photo syncing. I kept Contacts, Safari and Keychain connected as I do use them.

## End Result

The result of me doing this has been huge – I didn’t track speed before and after the change (I can only assume if I change back there is going to be an unnatural amount of network load as it kicks things off again) but the difference it has made to my perceived browsing speed is huge.