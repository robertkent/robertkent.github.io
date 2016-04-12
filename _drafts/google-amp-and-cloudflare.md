---
layout: post
title:  "Cloudflare and Google AMP"
categories: tutorial
image: "/assets/images/posts/cloudflare-and-google-amp/background.jpg"
---

#### A little about Google AMP

[Google AMP](https://www.ampproject.org/) (Accelerated Mobile Pages) is a new service from Google that has been designed to drastically speed up mobile content.

By caching your content, Google can serve your page exactly as it appears but without having to fetch any data from your own server.

You may already have seen (on your mobile device) some pages being shown in the Google SERPs with AMP written underneath. You'll notice that when you click on these items that the content is served by Google itself.

<amp-img width="743" height="891" layout="responsive" src="/assets/images/posts/cloudflare-and-google-amp/serps.jpg"></amp-img>

I have replaced the theme of this website to use Amplify (link in the footer) which has a built-in template for serving an AMP version of this blog.

#### Problems with Cloudflare

As this website is served through cloudflare initially the validator for AMP didn't work. This is due to cloudflare injecting it's own javascript into the content of the page.

There are typically 3 separate settings within cloudflare that you (currently) need to turn off in order to pass validation.

*	Rocket Loader
*	Mirage (for those of your with Enterprise Plans)
*	Email Obfuscation

<amp-img width="814" height="475" layout="responsive" src="/assets/images/posts/cloudflare-and-google-amp/cloudflare.gif"></amp-img>

Once this is done you should be able to validate your domain with the following url [robkent.co.uk/#development=1](https://robkent.co.uk/#development=1). Then within Google Chrome tools you should see the validation within the console.

<amp-img width="800" height="101" layout="responsive" src="/assets/images/posts/cloudflare-and-google-amp/google-chrome-console.jpg"></amp-img>

You can view the source for this fix on the [Google AMP github issues page](https://github.com/ampproject/amphtml/issues/2380).