---
layout: post
title:  "Securing Firefox"
date:   2015-06-26 12:23:00
categories: security tech firefox
---

Mozilla's Firefox web browser is a free and open source browser used by millions of people around the world, including myself. Firefox has always aimed _to protect and respect your private information_, according to [Mozilla][moz].

However, over the years through many questionable and controversial decisions made by Mozilla Firefox has become more and more bloated, and has deliberated implemented "features" that risk the safety and privacy of the user.
This blog post is about how to secure Firefox and make it safer than default. It requires access to the about:config in Firefox (accessed through the URL bar) which voids the warranty of the browser, but none of these changes have shown any documented evidence of affecting your browsing experience in a negative way.

A lot of this information was sourced from a HN article by Github user [amq][amq]. The original article and discussion can be viewed [here][hn]

## Google Safe Browsing 

This feature, while sounding beneficial on paper, essentially sends a list of any website you visit to Google who keep a list of malware/unsafe websites.

The problem with this is that it means Google, a company that is involved in the NSA's [PRISM][psm] surveillance program, tracks and checks the websites you visit. With a little common sense it is easy to browse the web safely without this feature enabled.

To disable, in about:config change:
<br>
```
browser.safebrowsing.enabled
browser.safebrowsing.downloads.enabled
browser.safebrowsing.malware.enabled
```

from "enabled" to "disabled"

## Firefox stats and telemetry ###

Firefox collects usage statistics, health reports and telemetry by default. While this information can be useful to Firefox developers, it should techinically be an "opt-in" feature by default. 

To disable, in about:config change:
<br>
```
datareporting.healthreport.service.enabled
datareporting.healthreport.uploadEnabled
toolkit.telemetry.enabled
```

from "enabled" to "disabled"

## WebRTC / Firefox Hello 

WebRTC, an experimental new in-browser audio and video technology, [leaks the real IP when using a VPN/TOR][vpn]. Firefox Hello connects to Telephonica, a Spanish service powering Hello without asking for the user's permission.

To disable, in about:config change:
<br>
```
media.peerconnection.enabled
loop.enabled
```

from "enabled" to "disabled"

## EME (Encrypted Media Extensions, DRM) 

EME is a binary plugin (closed-source) that has been included with Firefox since version 38. It enables playback of encrypted media and lets you use streaming services such as Netflix without Microsoft Silverlight. While this can be disabled, it still leaves a closed-source binary blob in your browser. To completely remove it one can either download an EME-free version from Mozilla [here][eme], or use a fork such as [Icecat][ic] which is maintained by the GNU Project.

To disable, in about:config change:
<br>

```
media.eme.enabled
media.gmp-eme-adobe.enabled
```

from "enabled" to "disabled"

## Pocket Integration 

Pocket is a third-party proprietary service for managing a reading list of articles. It essentially does the exact same thing as Firefox Sync (which is open source), and despite user feedback criticising the inclusion of Pocket Mozilla still include it by default.

To disable, in about:config change:
<br>

```
browser.pocket.enabled
```

from "enabled" to "disabled"

## Geo-location / tracking 

To disable, in about:config change:
<br>
```
geo.enabled
```

from "enabled" to "disabled"

## Search suggestions 

Depending on your search engine, everything you type into the search box is sent to that search engine's server (even if you don't press enter)

To disable, in about:config change:
<br>
```
browser.search.suggest.enabled
```

from "enabled" to "disabled"

-

## Further protection? 

The following addons and settings will further secure your Firefox.

- [uMatrix][um], a plugin with a point & click interface to forbid/allow any class of requests made by your browser. Use it to block scripts, iframes, ads, facebook, etc (replacement for Google Safebrowsing). Can also be used to manipulate refferal information, spoof your user-agent header and enforce strict HTTPS across sites.

- [uBlock Origin][ub], a low memory and fast adblocker which also disables malware domains (replacement for Google Safebrowsing). It has a lower RAM usage than Adblock Plus/Edge.

- [Self-destructing cookies][sd], a plugin which gets rid of a site's cookies and LocalStorage as soon as you close its tabs. Protects against trackers and zombie-cookies. Trustworthy services can be whitelisted.

- [Cookie Monster][cm], a plugin that provides proactive cookie management on a site or domain level basis, including 3rd party cookies. Via the status bar, it provides easy access to enhanced cookie functionality, while doing so in a non-intrusive manner.

And, in about:config enable
<br>
```
privacy.trackingprotection.enabled
```

This is the Firefox Tracking Protection feature (not to be confused with the Do Not Track feature, which only asks sites not to track you). Tracking Protection actively blocks sites that are known to track users.

## Sick of the direction Mozilla is taking Firefox?

I am one of these people. Rather than prioritising things such as sandboxing in Firefox, Mozilla continues to add more bloat to the point where the browser is almost an entire operating system.

However, because the code of Firefox is free and open source, not all is lost. Some good forks of Firefox include [Icecat][ic] by the GNU Project, [Iceweasel][iw] by the Debian Project and [Palemoon][pm] by Moonchild. See what works for you.

Sincerely,
<br>
Tom Hackshaw

[moz]: https://www.mozilla.org/en-US/firefox/desktop/
[amq]: https://github.com/amq/firefox-debloat
[hn]: https://news.ycombinator.com/item?id=9779440
[psm]: https://en.wikipedia.org/wiki/PRISM_(surveillance_program)
[vpn]: https://github.com/diafygi/webrtc-ips
[eme]: http://download.cdn.mozilla.net/pub/firefox/releases/latest/win32-EME-free/
[ic]: https://www.gnu.org/software/gnuzilla/
[um]: https://addons.mozilla.org/en-us/firefox/addon/umatrix/
[ub]: https://addons.mozilla.org/En-us/firefox/addon/ublock-origin/
[sd]: https://addons.mozilla.org/en-us/firefox/addon/self-destructing-cookies/
[cm]: https://addons.mozilla.org/en-us/firefox/addon/cookie-monster/
[iw]: https://wiki.debian.org/Iceweasel
[pm]: https://www.palemoon.org/
