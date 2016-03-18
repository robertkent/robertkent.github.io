---
layout: post
title:  "Setting up this website - using Jekyll, Cloudflare & Github"
date:   2016-03-16 19:15:09 +0000
categories: new website
---
Did you know you can set up a super-fast website for pretty much zero-money? It's really easy too!

Here are the steps:

*   Register your domain with any provider (someone where you can change some DNS records preferably!)
*   Sign-up with [Cloudflare](https://www.cloudflare.co.uk) (or login) and add your domain. A free account will do.
*   Point your NameServers to Cloudflare (can be found within your CloudFlare account)
*   Sign-up with [Github](https://github.com) (or login)
*   Create a new repository called "your-github-username.github.io" (replacing with your actual username)
*   Add a new file called CNAME to your repo with your domain name on the first line (e.g. robkent.co.uk)
*   Clone your repository locally - and create a new [Jekyll](https://jekyllrb.com/) site within it
*   Within Cloudflare - create and point 2x A-Records to the IP addresses by following the appropriate link on [this page within Github](https://help.github.com/articles/quick-start-setting-up-a-custom-domain/).
*   Wait for the DNS to resolve.

And that should be it!

All-in-all it takes around 30mins -1 hour but afterwards you should have a brand-new Jekyll-powered website like this one which is super-fast and hosted for free! (Just remember to keep renewing that domain!)