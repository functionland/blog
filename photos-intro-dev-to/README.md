---
title: Google Photos open-source alternative with React Native
published: true
description: An alternative for Google Photos that will always remain free because you'll keep your photos on your own hard drive!
tags: showdev, javascript, react, reactnative
cover_image: https://raw.githubusercontent.com/functionland/photos/main/assets/images/logo-rectangular.png
---

Greetings fellow DEVs! You've probably heard the news about Google Photos becoming a paid service starting this month. We've been eying this date for a while and were preparing something that we think is kinda cool! Drumroll please... Photos UI partially implemented in React Native! Here's a peek:

![Box Photos](https://raw.githubusercontent.com/functionland/blog/main/photos-intro-dev-to/photos.gif "Box Photos")

This implementation is backend-agnostic, you can fork the repo and implement an interface to connect it to your own backend! We're also working on an open-source p2p backend implementation, more on this later in the article.

If you like what you see, there are ways you can help us take it to the next level:

1. Star the repo [on GitHub](https://github.com/functionland/photos)!
2. Join [the discussions](https://github.com/functionland/photos/discussions),
tell us what you think about where it needs to go from here.
3. Contribute code! Photos is currently being maintained only by
[Ehsan](https://github.com/ehsan6sha), he's eager to welcome new collaborators!
4. We have lots of cool things planned, including a Kickstarter campaign! [Join the mailing list](https://groups.google.com/g/functionland)
to hear about all updates!
5. We're actively seeking funding, if you can help with this in any way, please [drop us a message](https://www.linkedin.com/in/keyvanmsadeghi/)!
6. You can also follow us on
[Twitter](https://twitter.com/functionland),
[Telegram](https://t.me/functionland) and
[YouTube](https://www.youtube.com/channel/UCAyjxikGGQTcJvjrhZyYhpA).

This is still at prototype stage and not ready for prime time, but we wanted to share early to hear your valuable feedback and hopefully have those of you who are interested join us to build a community around an ambitious yet noble goal:

## Ending *Big Tech*'s reign by building open-source **p2p** apps!

Making Photos paid? Really? Haven't Google already made billions by training AI models from our pictures and videos? Us [being the product](https://www.netflix.com/title/81254224) was not enough, we should also pay now?

I don't want to sound arrogant or ungrateful. Truth be told, I personally owe Big Tech a great deal! The very ability to write these words for example, I wouldn't know them if it wasn't for Windows (and me being a nerd)! And I was able to use Windows because a version of it existed that probably even Microsoft wasn't aware of: [MRT Windows](https://www.shouldiremoveit.com/MRT-Windows-XP-Farsi-Interface-Pack-24170-program.aspx)! (MRT being the initials of the dude who created it)

Being born into a country disconnected from the global economy, we didn't have legitimate access to software such as Windows, but *Mr. MRT* had *BitTorrent* and lots of blank CDs to cater us :) *p2p* was the missing piece to the puzzle: although we had in effect *unwarranted access* to Microsoft's *intellectual property*, a whole generation of developers was raised thanks to (unlawful) democratized access to software. Instead of the stereotypic *Jihadists* that the world expected, these people turned out quite civilized, some of them who moved abroad are now working for the Big Tech.

A large population of US citizens, meanwhile, didn't (by enforced law) have free access to Windows. Those who ended up attacking the Capitol in January might've acted different had they been using Windows as kids!

Hopefully the above example conveys the importance of free access to software, free both as in speech and as in beer!

### Does a workable solution for delivering and maintaining free software actually exist?

Yes and no. There are architectural and operational issues. We can, however, arrive at a solution by refactoring to [*Web 3.0*](https://medium.com/fabric-ventures/what-is-web-3-0-why-it-matters-934eb07f3d2b)! It helps us address several challenges:

#### 1. Servers are expensive, how to pay for them without charging the users?

True, any application with enough users comes with a big monthly AWS bill. But why isn't this an issue for dev tools? We've had top notch UIs even for niche use cases such as [state management in a specific library](https://github.com/tannerlinsley/react-query-devtools). Doh! These don't need a server :) our dev machines **are** the server for these
tools. Hmm... developers have their own servers, right...

What if users had their own **"Personal Server"** too? This model has worked for [Plex](https://www.plex.tv/) as an example, how about taking it one step further? Every house has a fridge for keeping food, would it make sense to also have a **"store of data"**? This is the main idea here, there's a niche who already have PCs at home (PC gamers, people still keeping their old PCs, etc.), we can write software that turns a PC to a server for a household's data needs.

In reality, the leverage that the Big Tech holds us hostage over is:

![HDD pile](https://raw.githubusercontent.com/functionland/blog/main/photos-intro-dev-to/PileHDD.png "Pile of HDDs")

For sure, serving the world population takes acres upon acres of data centers. But for a household? Wouldn't a Raspberry Pi and a few TB of HDD be enough? We can even package this in a gadget for it to be more appealing. We can also accommodate for Cloud features like reliable backups in this p2p setting, a copy of one's photos can be backed up at another location, e.g. parents' house.

*Concept for personal server, aka __"Box"__, read more on [fx.land](https://fx.land)*
![Box concept](https://raw.githubusercontent.com/functionland/blog/main/photos-intro-dev-to/box.png "Box concept")

#### 2. Doing both backend and frontend is hard

Absolutely! We need to fix this. Google and the like have armies of developers working on each app, how can anyone compete? Don't fret! We can seek help from millions of frontend JavaScript developers around the world! They are already building all kinds of cool apps. Backend is not really an issues, many of them are well versed at using serverless cloud functions. So if we can provide the same **"Developer Experience"**, can we have these brilliant people aboard?

To address the need for backend, and also the limited compute power of the hardware that may be used, the solution that we're currently implementing is **"Managed Services"**. For a start, we are developing 2 protocols on top of [libp2p](https://libp2p.io/):

* **File Protocol**: for uploading and downloading files, this provides the function of a traditional file server
* **Data Protocol**: for persisting JSON data. This would be the Web 3.0 equivalent of REST or GraphQL endpoints. By linking the JSON data with [DAG-JSON](https://specs.ipld.io/block-layer/codecs/dag-json), we also get the conventional database-like queries.

Work on more managed services are on the way. We'll need *Machine Learning* services for an app like Photos soon!

These managed services are packaged in a JavaScript module, `@functionland/graph`, so the complexities of what happens behind the scene is abstracted away for the app developer. They'll have an experience very similar to using serverless functions. Voila!

This work is being done in this repository:

[github.com/functionland/box](https://github.com/functionland/box)

#### 3. If an app is open source, how can the developer make a living from it?

This one is a long standing question in open source, and *Blockchain* may finally give us an answer. It's ironic that prominent blockchains such as *Bitcoin* have become somewhat centralized, true decentralization happens when
average people run validator nodes. That's not the case today, but if there is a future where every home has a server, true decentralization can start! Newer generation blockchains are way less resource intensive, take [Mina](https://minaprotocol.com/) as an example, a snapshot of the whole chain will always be 22KB! 

So we can have home servers also be blockchain validator nodes, effectively printing money around the clock! We can then have a decentralized version of an *App Store*, downloading and updating apps from this store can happen
on-chain and be paid. But users won't be paying out of pocket, they'll pay with a portion of coins mined on their server (freedom tax :).

This aspect is still very much at ideation stage, we'd would love to brainstorm and hear what you think about it.

#### 4. Would the User Experience be compromised in any way?

If anything, UX will be improved. There is no privacy concerns, users *physically own* their data. There's no advertisement, no lock-in. And in open source, anything that has use cases also has a community of contributors around it. So no longer we'll see useful apps become adware (anyone remember *ShareIt*?). No orphaned app stuck with last update years ago. All the cool things that we developers enjoy in the open source software we use, now up for grabs by the masses.

> Eagerly looking forward to hearing your comments! Please don't hesitate to bash the whole idea to the ground! We don't mind at all. Only in common wisdom shall we thrive, no one soul knows all, most definitely not the noobs who started this :) -- Love and peace, Functionland
