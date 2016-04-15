---
layout: post
title:  "Forcing HTTPS using .htaccess (with conditions)"
categories: snippets htaccess
---

With the major search engines preferring secure websites and free SSL certificates becomming more readily available, it's not just ecommerce websites that benefit from a secure website.

Here is a little bit of code that (if you're using an apache server with mod_rewrite support) will 301 redirect all of your web pages to their secure alternative.

Obviously, it goes without saying that you should try to secure as must as possible, however there are times when you may need to stop certain pages being presented as HTTPS (usually for some random 3rd party access) so I've included a few examples of how to include certain exceptions to the rule.

{% highlight htaccess %}

<IfModule mod_rewrite.c>
	RewriteEngine on

	# 1. First we check for an insecure connection
	RewriteCond %{SERVER_PORT} 80

	# a) How about preventing some IP address
	# from redirecting?
	RewriteCond %{REMOTE_ADDR} !^MYI\.PAD\.DRE\.SS$

	# b) How about preventing a certain URL
	# from being secure?
	RewriteCond %{REQUEST_URI} !^/my-certain-url$

	# c) How about preventing a certain directory
	# path from being secure?
	RewriteCond %{REQUEST_URI} !^/my_insecure_folder.*$

	# d) How about checking whther we're
	# on the correct url / subdomain?
	RewriteCond %{HTTP_HOST} ^www\.my-website\.co\.uk$ [NC]

	# 2. If we pass those conditions let's
	# rewrite anything to our secure version using 301
	RewriteRule ^(.*)$ https://%{HTTP_HOST}/$1 [R=301,L]

</IfModule>

{% endhighlight %}

A quick explanation

1\. We set the first condition to check for any insecure connection (port 80 as opposed to 443)
<ul>
<li>a) IP address prevention - useful e.g. if your server cron requires insecure CURL connection</li>
<li>b) URL prevention - e.g. a certain page needs to be accessed without HTTPS</li>
<li>c) directory prevention - e.g. media folder or other than needs non-secure connection</li>
<li>d) Checking for the website / subdomain - e.g. if you have a single file-base used through different domains</li>
</ul>
2\. We perform our rewrite rule (anything in the URL request after the domain to be re-written to the new domain structure)

That's about it really. Once you've done this you should also make sure your internal linking is pointing to your secure pages (this way search engines won't need to keep being redirected as they browse your internal linking structure).