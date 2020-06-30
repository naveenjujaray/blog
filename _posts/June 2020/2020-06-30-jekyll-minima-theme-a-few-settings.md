---
layout: post
title:  "Jekyll Minima Theme - A Few Settings"
date:   2020-06-30 16:00:03 +0530
categories: jekyll update
comments: true
permalink: "/minimathemesettings"
---
This post is a follow-up of my earlier post about building a jekyll site.

In this post, I will describe a few things that I modified on my site. For example, the footer show site title twice, I add a `_config.yml` setting to show blog author name instead of one of the site titles.

<h2>Add site description</h2>
The blog site that you deployed earlier (as described in the post referenced above) should look pretty good, but we can make a few quick improvements to make it look even better.

Add a variable `description` to your `_config.yml` and set its value to a short description of your site.

<b>_config.yml</b>
{% highlight ruby %}
description: This blog includes posts related to topic A, topic B and topic C.
{% endhighlight %}
Try in browser. The description now displays in footer.

<h2>Modify title above list of posts</h2>
On the Home/Index page, the list of posts are preceded by a title “Posts”. You can change it to a different title. Suppose, you want the title to be “Latest Posts”. This is easily achieved by adding a variable to `index.html`’s front matter:
{% highlight ruby %}
---
layout: home
list_title: "Latest Posts"
---
{% endhighlight %}
Try in browser. The Home page displays “Latest Posts” as the title above list of posts.

<h2>Add github, twitter and rss links to footer</h2>
Github, Twitter and RSS links can be added to footer by simply setting variables in `_config.yml`.

The link to RSS feed is already displayed at the end of list of posts on the Home page. But adding a variable in `_config.yml` and setting it to just `rss` also adds a link in the footer.

<b>_config.yml</b>
{% highlight ruby %}
github_username: your_github_username
twitter_username: your_twitter_username
rss: rss
{% endhighlight %}
Try in browser. Github, Twitter and RSS links are displayed nicely stacked in the footer.

<h2>Modify footer to display blog author name</h2>
Now the setting that I mentioned at the beginning of this post - displaying blog author name in the footer, instead of displaying site title twice.

The Minima theme displays the site title a second time, because it looks for site `author` variable and if the `author` variable is not present it uses `title` variable as default value.

So, to make this changes, you can simply add `author` variable to `_config.yml`.
{% highlight ruby %}
author: "Blog Author"
{% endhighlight %}
Try in browser. Footer should now display blog author name instead of site title be displayed a second time.

<h2>Google Analytics</h2>
You can add Google analytics to your site by adding the following setting to `_config.yml`:
{% highlight ruby %}
google_analytics: UA-XXXXXXXX-X
{% endhighlight %}