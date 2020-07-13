---
layout: post
title:  "Deploy a website using Firebase Hosting"
date:   2020-07-13 10:00:00 +0530
categories: [ Firebase, Hosting ]
image: assets/images/firebase/1.jpg
comments: true
permalink: "/firebase_hosting"
published: true
---
There's a lot of options cheap or even free in the market to deploy our projects. One of these and my favorite is the Firebase Hosting, a service of Google.

**Firebase** is a set of services of Google that provides you a **BaaS** (Back-end as a service), which means you don't have to worry about the boring part of deploy a back-end to your project. One of these services is the Firebase Hosting that you can deploy your website or web app made in HTML, Javascript, and CSS.

I'll show you how to deploy a simple website in the Firebase Hosting at zero cost.

## Create a project

We need to click in "Go to console" in the top right corner.

![no2](/assets/images/firebase/2.jpg)

So the Firebase console. Now, we gonna create a project by clicking in "Adicionar projeto" (I didn't find how to change the language on the firebase console)

![no3](/assets/images/firebase/3.jpg)

Now, we chosen the name of the project and keep on! In the mine, I've chosen the name "Firebase Lab"

![no4](/assets/images/firebase/4.jpg)

Here you can disable google analytics for now:

### The project finally created:

![no5](/assets/images/firebase/5.jpg)

# Deploy website
We gonna create a folder and a simple html:
{% highlight ruby %}
$ mkdir firebase-lab-website
{% endhighlight %}

### Look at our simple html in the folder:

**blog/index.html**
{% highlight ruby %}
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog</title>
  </head>
  <body>
    <h1>Text here</h1>
  </body>
</html>
{% endhighlight %}
### Now, we need to install the CLI of the firebase with the command below:
{% highlight ruby %}
$ npm install -g firebase-tools
{% endhighlight %}
### Now, we need login:
{% highlight ruby %}
$ firebase login
{% endhighlight %}
After that, execute this command in the website directory and choose the right project:
{% highlight ruby %}
$ firebase init
{% endhighlight %}

- First, you select the option "Hosting: Configure and deploy Firebase Hosting sites" with the space bar and press Enter.
- Second, choose the option "Use an existing project" by press Enter.
- Third, choose the project that you created.
- Fourth, enter the folder of your index.html. The default is "public", but in my case, is "./".
- Last, we need to say if your website is a single-page app.

All ready! Now, the last command in the directory is to deploy:
{% highlight ruby %}
$ firebase deploy
{% endhighlight %}

_Our website is online!!_

You can see details of the deploy in the option "Hosting" at the left menu:
![no6](/assets/images/firebase/6.png)
Give me feedback! :) Thanks!