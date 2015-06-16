---
layout: post
title:  "Security 101: If the service you use is free, then you are the product"
date:   2015-06-16 22:16:15
categories: security tech snowden
---

Email, social networks, instant messaging, cloud storage etcetera. All of these things are used by people over the Internet everyday. 
The big names: Google, Amazon, Microsoft, Yahoo, Apple, Facebook, Dropbox etc power the majority of these mainstream services.

Of the many things that were made clear from the Edward Snowden leaks, these companies violate the privacy and freedom of the user. What many people unfortunately don't realise when using these services is that _*they are the product that is sold and made a profit from by these very companies*_. In our post Snowden world it's easy to fall into security nihilism (i.e. "'they' know everything so why bother?") or to think you have nothing to hide.

The worst thing you can have is a false sense of security.

These companies often offer little to no transparency, whether it be their profit model or source code. Proprietary services and software traps the user and revokes their freedoms. With closed source software and services, you need to have 100% trust in the vendor because there's nothing except for their morality in the way of them leaking your personal information. Even if you can vouch for their integrity, proprietary software invariably has more uncaught security bugs and exploits because there are fewer eyes examining the source code.

## So, what do I do?

Use services that operate on a _clear_ transparency model. Good examples include, but are not limited to [mailbox.org][mb], [Kolab Now][kl], [Tutanota][tu], etc. These are examples of services that clearly have their source code shown, licensed under a permissive copyleft license and show their profit model.

The site [PRISM Break][pb] is a fantastic resource for finding user respecting services (and software), but I am going to list some personal favourites.

Search engines (alternatives to Google, Yahoo, Bing)

- [searx][searx], a fully free meta search engine that gets proxied results from multiple sources
- [Startpage][sp], a search engine which uses proxied Google searches, and has servers based in the Netherlands
- [Swisscows][sc], an independent search engine with servers based in Switzerland
- [Yacy][yc], a fully free and decentralised search engine written in Java

_Why is DuckDuckGo not listed?_
<br>
DDG has a few major flaws, the biggest being in that they use Amazon AWS servers which are hosted in the US. Also, their founder [doesn't have the best track record for respecting users' privacy][ddg]

Email (alternatives to Gmail, Yahoo Mail, Outlook)

- [Tutanota][tu], based in Germany with their source code publically available
- [mailbox.org][mb], based in Germany using FOSS to operate the site, and entirely on renewable energy
- [posteo][post], based in Germany using FOSS to operate the site, and entirely on renewable energy too!
- [Kolab Now][kl], based in Switzerland with their source code publically available

_Why is Protonmail not listed?_
<br>
Protonmail, while benefiting from being hosted in Switzerland, does not publish their source code.

For all of these services, use [PGP][PGP] to encrypt your emails for added security.

Cloud (alternatives to Drive, One Drive, Dropbox)

- [Kolab Now][kl]
- [ownCloud][oc], self-hosted 
- [pyd.io][pd], also self-hosted

Social Networks (alternatives to Facebook, Myspace, LINE)

- [Diaspora][dias], self-hosted decentralised and federated social network. Public instances exist where you can sign up if you don't have your own server. If you do sign up on a public Diaspora server, aim for those hosted in Germany, Austria, Iceland or Switzerland (countries with strict privacy laws)
- [pump.io][pump], very similar to Diaspora, only not federated

_Why is ello.co not listed?_
<br>
Ello does not publish their source code, despite many of it's users asking for it. It is also hosted in the US.

Video calling (alternatives to Skype, Hangouts, LINE)

- [Jitsi][jit], a fully free alternative to Skype with similar features
- [Tox][tox], a fully free messaging, voice and video software, currently in alpha
- [Mumble][mub], another fully free alternative to Skype

WebRTC is promising, however it is currently too experimental and unstable to use for secure use.

For any further info, go to [PRISM Break][pb] to find free and open source alternatives to proprietary services and software.



Sincerely,
<br>
Tom Hackshaw

[mb]: mailbox.org
[kl]: kolabnow.com
[tu]: tutanota.de
[pb]: prism-break.org
[searx]: searx.me
[sp]: eu.startpage.com
[sc]: swisscows.ch
[yc]: yacy.net
[ddg]: https://en.wikipedia.org/wiki/DuckDuckGo
[PGP]: https://emailselfdefense.fsf.org/en/
[post]: posteo.de
[oc]: owncloud.org
[pd]: pyd.io
[dias]: https://diasporafoundation.org/
[pump]: pump.io
[jit]: jitsi.org
[tox]: tox.im
[mub]: mumble.info
