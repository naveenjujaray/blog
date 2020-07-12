---
layout: post
title:  "Build A Blog Using Jekyll And Deploy To Github Pages And Set Custom Domain"
date:   2020-06-29 10:00:03 +0530
categories: [ Jekyll ]
image: https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQnVSoVtxiTxFVpd3FadZvxRuOynsRQZO-VXw&usqp=CAU
tags: [sticky]

comments: true
permalink: "/buildblogusingjekyll"
published: true
---
I recently decided to start a blog. I had used Wordpress in the past, so I knew I could get my blog up and running quickly using Wordpress. I was also slightly familiar with Jekyll. Doing a google search and reading a few blog posts educated me on benefits of Jekyll and static sites in general. I explored Jekyll a little more and loved it immediately.

The first thing that appealed to me about Jekyll was how programmer-friendly it was. Creating a site using Jekyll felt very similar to a developer’s day-to-day tasks. Another thing that appealed to me was Jekyll’s integration with GitHub Pages. Finally, free hosting provided by GitHub Pages (along with the ability to set custom domains) tipped my decision towards using Jekyll.

I have written this post to serve as a stand-alone tutorial, while also trying to keep it short. I briefly describe new terms and concepts as I introduce them, but do not go into much detail. Jekyll’s documentation is excellent and working through [Quickstart][Quickstart] and [Step-by-Step Tutorial][Step-by-Step Tutorial] should provide you good background on Jekyll.

Let’s get started
<h2>Install Ruby Development Environment</h2>

You need Ruby development environment setup on your computer. Jekyll documentation provides the requirements list here. In addition, you also need bundler. You can install bundler by using the command gem install bundler.

<h2>Install Jekyll</h2>

Jekyll is a ruby gem. Install it by running the following command in a terminal:
{% highlight ruby %}
$ gem install jekyll
{% endhighlight %}
<h2>Create a new directory for your site</h2>

On your computer, create a directory to hold your site:

<h2>Create index.html in the new directory</h2>
{% highlight ruby %}
$ cd my-site
{% endhighlight %}
Create `index.html` with some content, such as:

<b>index.html</b>

<h2>Serve the jekyll blog</h2>

In a terminal, run the following command
{% highlight ruby %}
$ jekyll serve
{% endhighlight %}

This command generates the site files and runs a local web server at `http://localhost:4000.`

<h2>Install theme gem</h2>

You can use a theme to improve your site’s presentation. There is a wide selection of themes to choose from. You can get started with `minima` theme which is provided by Jekyll. You can install `minima` gem using the following command:
{% highlight ruby %}
$ gem install minima
{% endhighlight %}
<h2>Create Gemfile</h2>

Create a file `Gemfile` in the root directory. `Gemfile` is used to specify which gems your Jekyll site uses.

<b>Gemfile</b>
{% highlight ruby %}
source 'https://rubygems.org'
gem 'minima'
{% endhighlight %}
<h2>Create Jekyll config file and add theme</h2>

You also need to set the theme in Jekyll’s configuration file. Jekyll reads configuration from a file named `_config.yml` in your site’s root directory. Create `_config.yml` with the following contents:

<b>_config.yml</b>
{% highlight ruby %}
theme: minima
{% endhighlight %}
After making any changes to `_config.yml`, you need to restart `jekyll serve` for Jekyll to pickup configuration changes. Even after restarting `jekyll` serve, you will notice no difference in your site’s rendering. You will fix this next.

<h2>Update index.html to use a layout</h2>

In the previous section, you saw that the text of your `index page` rendered without any styling from the theme. This is happening because Jekyll is treating your index.html as a regular html file. You can tell Jekyll to use the theme’s `home` layout by adding the following to the top of your `index.html`:
{% highlight ruby %}
---
layout: home
---
{% endhighlight %}
This is called the front matter. Jekyll does additional processing on any file containing a front matter.

Minima theme provides a `home` layout which is most suitable for a site’s index page. Among other things `home` layout adds a list of recent posts to the home page.

Try in browser. The index page of the site now renders in theme.
<h2>Add site title to config</h2>

With the site rendered in theme, it looks really good. Like most sites, you want your site to have a title too. The `minima` theme uses `title` variable’s value (if available) as title of your site. You can set `title` variable by adding the line `title: MyAwesomeBlog` to `_config.yml.` Your `_config.yml` should look like this now:

<b></b>
{% highlight ruby %}
theme: minima
title: MyAwesomeBlog
{% endhighlight %}
Restart `jekyll serve` and refresh browser. You will notice that the value for title that you provided in `_config.yml` now becomes the title of your site.

<h2>Create about page</h2>

Create an About page by creating a `about.md` file in the site’s root directory.

<b>about.md</b>
{% highlight ruby %}
---
layout: page
title: About
---
{% endhighlight %}
# About me
This page will contain information about me.

This file uses the `page` layout provided by the theme.

Try in browser. About link shows up in top bar. Jekyll automatically adds any html or markdown files that are in your root directory to navigation bar, using value of the variable `title` from the page’s front matter as link text.

<h2>Create projects page</h2>

Add another page to your site. Create `projects.md` in the site’s root directory.

<b>projects.md</b>
{% highlight ruby %}
---
layout: page
title: Projects
---
{% endhighlight %}
# Projects
Projects will be listed here.

Try in browser. The navigation bar now shows Projects link too. Clicking on projects takes you to projects page.

<h2>Ordering navigation items</h2>

With `about` and project pages added, the site is in good shape now. Suppose you want modify the order of items in the navigation bar with About appearing to the right of `Projects`.

All top-level pages are added to navigation bar in alphabetical order. Reordering navigation items is easily done by using `header_pages` configuration setting. Add `header_pages` to configuration and set its value to a list of pages in the order you wish them to appear.

<b>_config.yml</b>
{% highlight ruby %}
theme: minima
title: MyAwesomeBlog
header_pages:
  - projects.md
  - about.md
{% endhighlight %}
Try in browser. The `About` and `Project` items now appear in your preferred order.

<h2>Add a blog post</h2>

Creating a `blog` post is as simple as creating a directory and a file within that directory.

Create a folder called `_posts` in the root directory of your site. Create a markdown (or html) file with year, month and day prefixed to the filename.
{% highlight ruby %}
$ mkdir _posts
$ cd _posts
{% endhighlight %}
Create a markdown file with year, month and day prefixed to the filename:

<b>2018-09-12-my-first-post.md</b>
{% highlight ruby %}
---
layout: post
---
{% endhighlight %}
This is the contents of this blog `post`.
Notice that this file contains Jekyll front matter and sets the layout to post, which is another layout provided by `minima` theme.

Try in browser. The site lists the post you just added. Clicking on the post title takes you to the post. Notice that the hyphen separated text portion of the file name becomes the title of the post. Also notice that a link to RSS feed is added.

<h2>Adding author name to post</h2>

In the blog post, you will notice that there is no author name being displayed. Jekyll minima theme supports `author` name setting. It just needs `author` variable to have a value. You can set author variable in the front matter of your post. Since it is likely that all posts on your site are written just by you, it is simpler to set `author` once in `_config.yml`.

Add the following to `_config.yml`:
{% highlight ruby %}
  - scope:
      path: ""
    values:
      author: "Blog Author"
{% endhighlight %}

`defaults` is special Jekyll setting that allows you to set front matter defaults. `path` under `scope` specifies which files this rule applies to. A blank path means the rule applies to all files in the site.

Restart `jekyll serve` and refresh browser page. The post now displays author name.

<h2>Deploying to GitHub Pages</h2>

This section describes how to host your site on GitHub Pages. GitHub allows you to host one user-level site on github pages. The github pages site for your github account should be created in a repository with the name username.github.io, where username is your GitHub username.

* create a repository on GitHub with the name username.github.io.
* add the github-pages gem to Gemfile. This is a gem provided by GitHub to manage Jekyll and its dependencies. Read this for more details.

<b>Gemfile</b>
{% highlight ruby %}
source 'https://rubygems.org'
gem 'minima'
gem "github-pages", group: :jekyll_plugins
{% endhighlight %}

* commit and push to your repository.
* after a couple of minutes you can point your browser to http://username.github.io and your should see your site.


<h2>Using a custom domain</h2>

You can set a custom domain for your site you just deployed as follows:


* purchase a domain name using service of your preference.
* in the root directory of your blog site, create a file `CNAME`.
* add the domain name as file’s contents.

<b>CNAME</b>
{% highlight ruby %}
myawesomedomain.com
{% endhighlight %}
* commit and push the changes to your gitub repository.
* to connect the domain name to your site, you need to update `ALIAS`, `A` or `ANAME` records with your domain register.
* for example, GoDaddy uses `A` records. If you registered your domain using GoDaddy, you can use IP addresses listed in this article to set `A` records.
* set the `www` subdomain to redirect to `myawesomedomain.com` by adding a `CNAME` record with your domain register. This is not to be confused with the `CNAME` file that you created earlier.
* if GoDaddy is your domain register, no action needs to be taken. GoDaddy automatically sets the `CNAME` record.


<h2>Add Disqus commenting</h2>

Comments are essential component of any site. minima supports Disqus commenting system. Comments can be enabled for your posts by setting a configuration parameter. There are steps to add comments to your site:

* sign-up for Disqus Basic account.
* on Disqus, add your site as organization (you will use `myawesomedomain.com`).
* in your site’s `_config.yml`, enable Disqus commenting by adding the following:
* 
<b>
_config.yml</b>
{% highlight ruby %}
disqus:
  shortname: <site-shortname-from-disqus>
  {% endhighlight %}
commit and push changes to your github repository.
After github pages regenerates the site in a few minutes, navigate to `myawesomedomain.com` in your browser. You should see Disqus comments displayed at bottom on your post page. Note that Disqus comments are not displayed when running the site locally using `jekyll serve`.

<h2>Conclusion</h2>

This post described how you can deploy your personal blog to GitHub Pages hosted site. We used Jekyll site generator since that is the technology that GitHub Pages uses internally. We saw how easy and quick it was to get a basic site up and running. Creating a post was equally straight-forward. Finally, we applied a custom domain to our site.

[Quickstart]: "https://jekyllrb.com/docs/"
[Step-by-Step Tutorial]: "https://jekyllrb.com/docs/step-by-step/01-setup/"
