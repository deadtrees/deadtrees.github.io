---
layout: post
title:  "How to host your site using Github Pages"
date:   2015-06-26 13:51:55
categories: tech
---

Millions of people around the world use [Github][gh] to code socially. One of the services Github offers for free is [Github Pages][gp], free static site hosting for you and your projects.

Most of my sites, including this blog, are hosted using Github Pages. It offers free hosting, [Markdown][md] (or similar) syntax out of the box using [Jekyll][jk] and a free .github.io domain name (with the option of using your own custom domain name such as www.example.com).

## 1. Create an account on Github

Head over to [Github][gh] and create an account. Once you have verified your email address and chosen your username [create a repository][repo] called _username_.github.io, where your username is the one you chose when creating your account.

## 2. Commit, and publish your site

In the repository page, click on the settings icon. Here, you can choose to automatically generate a Jekyll site if you don't want to code manually yourself and choose from a selection of themes. When you find a theme you like, click *Publish page*. These sites can be edited through either using the Github site, the Github client for Windows and Mac or using the command line (via SSH).

## 3. Pointing a custom domain name to your site

Create a file in your repository called "CNAME". In this file, include the url of your domain name (without the www) _e.g. example.com_ and commit the file.

Then, with whoever you used to register and buy your domain, use the cPanel to create a CNAME record pointing to username.github.io, with username as your own.

Refresh the page and your site will load up under example.com rather than username.github.io

This also works for subdomains (blog.example.com) too. Just have "blog.example.com" in your CNAME file rather than example.com

## Important to note

Remember, because you are hosting a site on a open source repository it means that they are all publicly available on the Internet, even if their repositories are private. If you have sensitive data in your Page repository, you may want to remove it before publishing. Pages are served over HTTP by default, not HTTPS, so you shouldn't use them for sensitive transactions, like sending passwords or credit card numbers.

Sincerely,
<br>
Tom Hackshaw

[gh]: https://github.com
[gp]: https://pages.github.com
[md]: https://en.wikipedia.org/wiki/Markdown
[jk]: http://jekyllrb.com
[repo]: https://github.com/new
