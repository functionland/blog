# Google Photos open-source alternative with React Native

Greetings fellow DEVs! You've probably heard the news about Google Photos
becoming a paid service starting this month. We've been eying this date for a
while and were preparing something that we think is kinda cool. Photos UI in
all its glory ported to React Native! Here's a peek:

TODO: GIF

TODO: github, give it a start, there's gonna be Kickstarter , subscribe to mailing list, assume reader stops here

read on!

This is still at prototype stage and not ready for prime time, but we wanted to
share early to hear your valuable feedback and hopefully have those of you who
are interested join us to build a community around an ambitious yet nobel goal:

# Ending the reign of the *Big Tech* by building open-source **p2p** apps!

I don't want to sound arrogant or ungrateful. Truth be told, I personally owe
Big Tech a great deal! The very ability to write these words for example -- I
wouldn't know them if it wasn't for Windows (and me being a nerd)! There was a
version of Windows that probably even Microsoft wasn't aware of:
[MRT Windows](https://www.shouldiremoveit.com/MRT-Windows-XP-Farsi-Interface-Pack-24170-program.aspx)!
(MRT being the initials of the dude who created it)

Being born into a country disconnected from the global economy, we didn't have
legitimate access to software such as Windows, but *Mr. MRT* had *BitTorrent*
and lots of blank CDs to cater us :) *p2p* is the other piece to the puzzle:
although we were in effect using *intellectual property* of Microsoft
unwarranted, a whole generation of developers was raised thanks to (unlawful)
democratized access to software.
Instead of the stereotypic *Jihadists* that the world expected, these people
turned out quite civilized, many of them who moved abroad are now working for
the Big Tech. A large population of US citizens, meanwhile, couldn't (by
enforced law) have access to Windows and some of them ended up attacking the
Capitol this January!

Hopefully the above example conveys the importance of free access to software,
free both as in speech and as in beer!

## Does a workable solution for delivering and maintaining free software actually exist?

Yes and no. There are architectural and operational issues. We can, however,
arrive at a solution by refactoring to *Web 3.0*! This helps us address several
challenges:

### 1. Servers are expensive, how to pay for them without charging the users?

True, any application with enough users comes with a big monthly AWS bill.
But why isn't this an issue for dev tools? We've had top notch UIs even
for niche use cases such as
[state management in a specific library](https://github.com/tannerlinsley/react-query-devtools).
Doh! These don't need a server :) our dev machines **are** the server for these
tools. Hmm... developers have their own servers, right.

What if users had their own **"Personal Server"** too? This model has worked
for the likes of [Plex](https://www.plex.tv/), how about taking it one step
further? Every house has a fridge for keeping food, would it make sense for it
to also have a **"store of data"**? This is the main idea here, there's a niche
who already have PCs at home (gamers, people still keeping their old PCs,
etc.), we can write software that turns these PCs to a server for a household's
data needs.

In reality, this is the leverage that the Big Tech holds us hostage over:

![HDD pile](./PileHDD.png "Pile of HDDs")

For sure, serving the world population takes acres upon acres of data centers.
But for a household? Wouldn't a Raspberry Pi and a few TB of HDD be enough? We
can even package this in a gadget for it to be more appealing. We can also
accommodate for Cloud features like reliable backups in this p2p setting, a
copy of one's photos can be backed up at another location, e.g. parents' house.

### 2. Doing both backend and frontend is hard

Absolutely! We should fix this. Google and the like have armies of developers
working on each app, how can anyone compete? Don't fret! We can seek help from
millions of frontend JavaScript developers around the world! They are already
building all kinds of cool apps. Backend is not really an issues, many of them
are well versed at using serverless cloud functions. So if we can provide the
same **"Developer Experience**, we can have these brilliant people aboard!

To address the need for backend, and also the limited compute power of the
hardware that may be used, the solution that we're currently implementing is
**"Managed Services"**. For a start, we are developing 2 protocols on top of
[libp2p](https://github.com/libp2p/js-libp2p):

* **File Protocol**: for uploading and downloading files, this provides the function
of a traditional file server
* **Data Protocol**: for persisting JSON data. This would be the Web 3.0
equivalent of REST or GraphQL endpoints. By linking the JSON data with
[DAG-JSON](https://specs.ipld.io/block-layer/codecs/dag-json), we also get the
conventional database-like queries.

These managed services will be packaged in a JavaScript module,
`@functionland/graph`, so the complexities of what happens behind the scene is
abstracted away for the app developer. They'll have an experience very similar
to using serverless functions. Voila!

This work is being done in this repository:

[github.com/functionland/box](https://github.com/functionland/box)

### How can developers make a living out of this?

Google Play alternative, OSS coin.
