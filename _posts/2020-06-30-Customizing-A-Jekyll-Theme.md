---
layout: post
title:  "Customizing A Jekyll Theme Layout"
date:   2020-06-30 06:00:03 +0530
categories: jekyll update
comments: true
---
After I started a blog, as described in [this][this] post, I felt it would be cool to convert the author name shown on top of each post to a link to the `about` page. This was a minor change, but it required me to customize `minima` theme’s `post` layout.

I describe the steps that I used to customize `minima’`s `post.html` layout in this post.
#Customizing theme files

You can modify a jekyll theme’s functionality by copying a specific file from theme gem and then modifying it. Jekyll uses local files of the same name to override the theme behavior. In addition, the local folder name has to be identical to the folder name in gem where you copied the file from.

#Create a folder in your site root directory
Since you are modifying the `post` layout, you need create a copy of the file in your local site. You need the following steps:

In the root directory of the site, create a `_layouts` directory:

{% highlight ruby %}
$ mkdir _layouts
{% endhighlight %}

#Locate minima gem’s post.html on your computer
You need to determine where Ruby gems are stored on your computer.

You can figure out Ruby gem folder location by running the command `gem environment` and looking for the value of `INSTALLATION DIRECTORY` field. The command output should look something like:
{% highlight ruby %}
$ gem environment

RubyGems Environment:
  ...

  - INSTALLATION DIRECTORY: /path/to/your/ruby/installation/lib/ruby/gems/2.3.0

  ...
{% endhighlight %}
The `minima` gem files are located within this folder:
{% highlight ruby %}
$ ls -l /path/to/your/ruby/installation/lib/ruby/gems/2.3.0/gems/minima-2.5.0
{% endhighlight %}

The file you want to copy and modify is located within the `_layouts` folder:

{% highlight ruby %}
$ ls -l /path/to/your/ruby/installation/lib/ruby/gems/2.3.0/gems/minima-2.5.0/_layouts
default.html
home.html
page.html
<b>post.html</b>
{% endhighlight %}

An alternative way to figure out the location of gem files is by using the command `bundle show minima`.

#Copy the gem post.html to your site
Copy `_layouts/post.html` from minima ruby gem folder into the local `_layouts` directory just created. Go to your site’s root directory and then run the following commands:

{% highlight ruby %}
$ cd _layouts
$ cp /path/to/your/ruby/installation/lib/ruby/gems/2.3.0/gems/minima-2.5.0/_layouts/post.html .
{% endhighlight %}

#Make author name a link
Open `post.html` in an editor and locate the line that you want to modify. The html that you want to modify is shown below:

{% highlight ruby %}
<span itemprop="author" itemscope itemtype="http://schema.org/Person"><span class="p-author h-card" itemprop="name">Naveen Jujaray</span></span>
{% endhighlight %}

Add an anchor element around `{{ page.author }}` as follows:

{% highlight ruby %}
<span itemprop="author" itemscope itemtype="http://schema.org/Person"><span class="p-author h-card" itemprop="name"><a href="/about.html">Naveen Jujaray</a></span></span>
{% endhighlight %}
Try in browser. In the post, the author name should now be a link. Clicking on the author name should take you to the about page.

[this]: https://njblog.onrender.com/jekyll/update/2020/06/29/Build-A-Blog-Using-Jekyll.html