---
layout: post
title: Useful softwares
---


<div class="message">
  Please note that i don't monitor the state of the links over time, so the links may break at some point. I'll try to keep them updated, and include more links if i stumble onto something i think is interesting.
</div>

As i'm doing a lot of system administration for my work or my personal rig, i told myself it could be useful to store (and share ?) a list of software i find interesting or that i have testes or used.

I split this listing in 2 categories: the server-side software (self or remotely-hosted) and desktop-side software.

## Server-side software

I have a small Windows PC (ITX sized PC with ryzen 7 2700X + GTX 1080 and 32G of 3ghz DDR4 with XMP profile) that i use for game or content streaming within my local network.
This PC hosts a small linux mint VM over Hyper-V that i use as a server.
This VM is also administrate using [webmin](https://www.webmin.com).

As of 2022, I'm preparing a migration of my services to a new VM based on Alma linux (long-term server OS compatible with RHEL/CentOS pre-stream).

### Messaging platform

- [Mattermost](https://mattermost.com/download/) : It is a really great alternative to slack. I happend to have prepare a mattermost instance (based on their opensource "Team" version). The programm works pretty well and they have greatly improved their UI accessibility over the years.  
- [Jitsi meet](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-start) : i happend to have tested a bit jitsi meet (both in the [jitsi meet instance](https://meet.jit.si) and in self hosted) for visioconferences and screensharing. It was working well in my test (i had some difficulties with screen sharing but it was expected.)
- [Element.io](https://element.io) : To be tested with self host using [this tutorial](https://cyberhost.uk/element-matrix-setup/), but should be able to replace a discord server. I a thinking of testing it for personal hosting, and possibly to replace mattermost as we may need to do audio meetings (with my work, i don't really need webcam, and i don't find visual calls to be usefull in general if no data is to be shared like screen sharing or presentation).
- Teams : i happend to have tested MS teams for work. Except sharepoint and office online integration, i can't say i really appreciate the experience (especially when working on my work MacMini): The UI is sluggish and the integrated office tends to crash when working on complex document or large excel files. Except for the meetings aspect (that was not working very well for me and could be replaced by a jitsi meeting room), slack or mattermost behaves better and are more usefull for text-base content.

### Organization software

For code project management, as visibily is a very important nowadays, i have quite recently started to use github heavyli.
(Before, I used github repos over ssh on my rig for small not-to-be-published projects or personnal scripts)

I have tested some git interfaces like gitlab (but it was a long time ago and i did not took time to finalize the install).
I found Gitea to be very easy to deploy and use (but more restrained on the functionnality).

As an alternative, BrailleNet use gitolite to manage repos, which is far more easier to manage for advanced users that have visual impairments and use specific hardware like braille keyboards.

For time and project management, for now i mainly use a google calendar with the TimeSheet plugin to manage my work time on project, but its kind of limited and i thinking of switching to a different kind of tools.
I'm planning to migrate my personnal time and project organization to nextcloud using some apps detailed below in the data sync section.

### Content streaming

I have my own Plex instance from content streaming on my device, even my chromecast. It works pretty well, even in a virtual instance.

### Data sync

I happen to have tested several personnal cloud tools in the past years.
- [Syncthing](https://syncthing.net) : i tested this bittorent based "sync" tool, but i had several issues putting it to work properly
- [NextCloud](https://nextcloud.com) : Maybe the most full-feature platform i tested for cloud sync, but i was not sure i needed all the "document view and edition" part of it.
I think it's a pretty good alternative/replacement of google drive or onedrive with file sync.
- [Seafile](https://www.seafile.com/en/home/) : A bit less features than nextcloud but is pretty performant. it's the one i'm using right now.

For the coming year, i'll be switching back to NextCloud to store and sync my personnal files. I also want to test the groupware and talk modules.
I'm planning to test those plugin and functionnality, like :
- [TimeManager](https://apps.nextcloud.com/apps/timemanager) to monitor my time on project tasks
- [Passwords](https://apps.nextcloud.com/apps/passwords) to manage my password
- [Forms](https://apps.nextcloud.com/apps/forms) to create and share simple forms to share
- [News](https://apps.nextcloud.com/apps/news) to centralize rss feeds (not much of an rss user right now, but i'd like to try this out)
- [Deck](https://apps.nextcloud.com/apps/deck) to manage projects task order and ideas

### P2P client with web interface

I'm doing a bit of P2P, and i did not find anything better than transmission as open-source bittorent client that can be found as daemon with a webinterface.

## Desktop-side software

### Utilities

- Data recovery with [TestDisk](https://www.cgsecurity.org/wiki/TestDisk_FR)
Note: i learned that a lot of "scam" software are selling UI on top of TestDisk for data recovery.

- Virtual KVM (sharing mouse and keyboard across different PC) with [Barrier](https://github.com/debauchee/barrier), a fork of synergy. I don't use it yet but i'm thinking of using it for advanced virtualization workspace with side-by-side Linux or MacOS and Windows guests on a virtualization rig. Just ound some [OSX-KVM intel for QEMU/KVM](https://github.com/kholia/OSX-KVM)

### For programming

I mainly use sublime text and merge solutions for my work (but the cost may be a bit blocking, and i usually prefer open-source and multiplatform solution).
When i don't have sublime text/merge available (work rig with windows), i usually rely on Visual Studio Code as generic code editor.
I used a lot Atom in the past, but i had too many issues on very big projects and with packages.

For anyone working on Unix and doing some remote programming on server, i would recommend learning to use Vim (most complex but extremely complete text editor in the console).
Just keep a comprehensive [cheatsheet](public/files/10-Best-VIM-Cheat-Sheet-01.jpeg) on hand :) : 

<img src="public/files/10-Best-VIM-Cheat-Sheet-01.jpeg" />
