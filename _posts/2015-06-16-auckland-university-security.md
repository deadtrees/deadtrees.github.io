---
layout: post
title:  "A disaster waiting to happen - the fragile Opsec at the University of Auckland "
date:   2015-06-16 9:00:15
categories: security uoa
---

A system that has been duck-taped together is bound to fail.

This post may be relevant to those thinking of enrolling into the University of Auckland, or to those already involved.

Last year when I started at the university I noticed that almost all of the IT services offered by the university are outsourced to third parties. These include:

- The student/staff email system, which is powered by Gmail
- The entire university login system, which is run on top of Oracle’s Peoplesoft
- The login system to access JSTOR and other databases runs on OCLC’s Ezproxy
- *All* of the university website pages have Google Analytics

This presents many security risks to both students and staff at the university. Because a lot of this software is run by third party companies (Google), or the service itself is proprietary “enterprise” software, this is a huge security hole. In the case of the email system, it means that the university are allowing Google access to ALL emails that students and staff send and receive using this system. It means that Google, whose profit model is that of advertising (selling user information to third party advertising companies who then push “personalised” content to the user) is data-mining all of the users [1].

Remember, Google made 91% of its net profit last year on this advertising model alone [2]. This is how Google became as big and wealthy as it is today.

Despite the fact that the university has a more than capable Computer Science and Software Engineering Department, they are choosing to pay Google monthly to host this email service rather than host their own in-house service that they have full control of. Such decisions are unprofessional and potentially endangers the students and staff of the university. Even if the university uses a third-party service with the same ethical principle as a service like [Kolab Now][kolab] or [Posteo][post] it would be better than the current system.

Why/how does it endanger students and staff? Suppose someone from the University of Auckland is a strong critic of the US government, and is using the university email system to communicate to other critics. Because Google is part of the NSA’s PRISM program [3] it means that the NSA have direct access to all emails and can profile the user through data-mining (XKEYSCORE). Since New Zealand's GCSB is part of the Five Eyes Intelligence Network (FVEY) the NSA can share any gathered information with the GCSB and the government.

There is then the illusion of security that the university offers as well.

Firstly, the SSL version of the University of Auckland’s website is full of holes. On ssleuth it shows that auckland.ac.nz, www.auckland.ac.nz and its CDN uses TLS RSA with RC4 128 SHA, a cipher suite that has been broken for years [4]. On ssleuth it scores a 3.7/10. Compare this with a mainstream website like Soundcloud, which scores an 8.8/10. The subdomain www.library.auckland.ac.nz isn’t even encrypted at all and loads over plain HTTP.

Even my own site [tomhackshaw.com][th] and all of my subdomains, which are delivered through Cloudflare's Content Delivery Network, score 9.0/10. 

_It’s 2015._ Things like this are inexcusable. These pages are insecure and are vulnerable to Man-in-the-Middle attacks as well as cross site scripting (XSS) attacks. Anyone with even the most basic understanding of Infosec and Opsec knows the danger of having a site that has only been partially secured.

Secondly, the university offers free Wi-Fi for anyone on campus, allowing anyone with a university login to access one of the Wi-Fi points and connect to the Internet. The problem with this is that the students and the staff are not taught of the insecurities of public Wi-Fi hotspots. There are things you should do and things you should only do on a trusted home connection. Namely, anyone who opens up Wireshark or a similar sniffer program can steal login credentials to those accessing Facebook or some other site over this connection.

Come on Auckland University, let's get it right.



Sincerely,
<br>
Tom Hackshaw

UPDATE - Looks the Auckland University homepage [auckland.ac.nz][au] nows uses modern crytography for their SSL certificate, scoring a 9.0 on ssleuth and scoring a B on Qualys SSL Labs. It would score higher if it did not accept the RC4 cipher which is depreciated, and supported Forward Secrecy. Otherwise thank you Auckland University for securing the site.

<br><br>
[1] <a href="https://nakedsecurity.sophos.com/2014/03/18/google-sued-for-data-mining-students-email/">https://nakedsecurity.sophos.com/2014/03/18/google-sued-for-data-mining-students-email/</a>

[2] <a href="http://fortune.com/2010/07/29/google-the-search-party-is-over/">http://fortune.com/2010/07/29/google-the-search-party-is-over/</a>

[3] <a href="https://en.wikipedia.org/wiki/PRISM_%28surveillance_program%29">https://en.wikipedia.org/wiki/PRISM_%28surveillance_program%29</a>, <a href="http://www.theguardian.com/world/2013/aug/23/nsa-prism-costs-tech-companies-paid">http://www.theguardian.com/world/2013/aug/23/nsa-prism-costs-tech-companies-paid</a>

[4] <a href="https://en.wikipedia.org/wiki/RC4">https://en.wikipedia.org/wiki/RC4</a>, <a href="https://community.qualys.com/blogs/securitylabs/2013/03/19/rc4-in-tls-is-broken-now-what">https://community.qualys.com/blogs/securitylabs/2013/03/19/rc4-in-tls-is-broken-now-what</a>

[kolab]: https://kolabnow.com
[post]:  https://posteo.de
[th]:    https://tomhackshaw.com
[au]: https://auckland.ac.nz

