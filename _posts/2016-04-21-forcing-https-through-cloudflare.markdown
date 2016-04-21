---
layout: post
title:  "Forcing HTTPS through Cloudflare"
categories: tutorials cloudflare
---
If you're lucky enough to be using cloudflare with your domain (and you should be as it's FREE), then you may want to know how to quickly and easily force https for an entire domain.

We'll it's as simple as:

1. Login to Cloudflare
2. Click on the Page Rules icon
3. Create new Page Rule
4. Enter your http domain followed by an asterix in the field provided e.g. "http://robkent.co.uk/*"
5. Click Add Settings
6. Select "Always use HTTPS"
7. Click Save & Deploy

Here's a quick GIF to illustrate:

<amp-img width="1040" height="642" layout="responsive" src="/assets/images/posts/force-https-using-cloudflare/force_https_using_cloudflare.gif"></amp-img>