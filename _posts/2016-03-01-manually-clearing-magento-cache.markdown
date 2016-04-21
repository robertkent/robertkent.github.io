---
layout: post
title:  "Manually Clearing Magento Cache"
categories: snippets magento
---

There are times when you may have edited Magento and inadvertently locked yourself out of the admin panel. Possibly changing some config data directly through the database.

Well, you need to clear the cache but can't access the admin, so what can you do?

Easy, simply open up your Magento directory and **delete / rename** the **/var/cache** folder!

As long as your permissions are set correctly, Magento will automatically create a new cache folder and all will be well in the world.