---
layout: post
title:  "What is Gatsby JS and Why Use It?"
date:   2020-07-16 06:00:00 +0530
categories: [ Web Development, Hosting ]
image: assets/images/firebase/9.png
comments: true
permalink: "/whats-gatsby"
published: true
---
## What Is Gatsby JS?
Welcome! In this article we are going to learn about Gatsby JS, what it is and why you would use it.

So let’s start with the question, `“What is Gatsby?”`
> Put most simply, Gatsby is a static site generator.
Now what does that mean?
## What is a Static Site Generator?

The static site part of this means that what Gatsby will produce for us are static HTML files that we load up on to a server.

Now this works differently than how a lot of websites work where you visit a website and it has to go query a database or do some programming on the server itself in order to serve your web pages.

So Gatsby is going to break that convention and have all of the stuff `already pre-configured` ahead of time and `just serve` that up.

> It’s important to point out that static sites do not mean not interactive or not dynamic.
So, we can load JavaScript into the HTML files that Gatsby serves as well as make API calls do interactions and build incredibly rich and immersive sites even though they are static in their nature of just being HTML files served up `without` programming `server-side` languages running.

So that’s the static side of things.
> Gatsby is also a generator. This means that Gatsby is actually a tool we run on our computer most commonly, although you can run Gatsby on a server, and it is going to generate content for you.

In the common setup that we’ll practice here we run Gatsby `locally` on our computer when we’re building a site and then we generate out the final finished product that Gatsby will spit out, which is a `Gatsby static site`, and again this will `include` `HTML CSS JavaScript images` all the stuff that we need for our site to run, Gatsby will generate it for us so we want to think of Gatsby as a tool that will help us build a final product but we’re not just like in queueing and throwing Gatsby into an existing site necessarily.

In order to do all of this generation Gatsby is going to use Node JS. Node will be running in a development environment on your computer itself. However the final sight when you ship a Gatsby sight live because it’s static it will not need Node JS on the server itself.

It’s using node to help generate the files as part of its tooling system but the final result does not require node to run on the server side.
## Gatsby JS Uses GraphQL
One of the great things about Gatsby is that it’s going to use the `GraphQL` querying `language` to get data from anywhere.

If you’re not familiar with `GraphQL`, it is an evolution of how to make `API` calls simpler and more efficient. And it’s a really great tool that you’re probably going to enjoy getting into if you don’t already know it.

> The most exciting part of this is that we can get our data into a Gatsby site from anywhere!

We could use `markdown` files, we can access databases, we could hook into common CMS’s like `WordPress` and `other` headless CMS, as well as even just a `CSV` file.

Because we have node running in our development environment and we have this GraphQL language, we have a huge range of abilities of what we could do to pull data into Gatsby itself.

This is important to remember that Gatsby is not going to handle our data for us rather it will get that data pulled into Gatsby and generate the site from that data.

## Gatsby Uses React for Templates
Gatsby also uses `React` and CSS which hopefully you’re familiar with. React is going to be used for all of the templates and CSS for the styling.

So, GraphQL will pull in our data, React will take care of what the template should look like and the styling is CSS. Then finally everything will be exported out into that final, super fast static Gatsby site.

## Gatsby Has a Rich Plugin Ecosystem
I also want to mention that Gatsby is built with a `plugin architecture` and this is a great system.

Because what we’re serving up is a static site how we go about interacting with JavaScript and other things can get a little complicated. So it’s really nice that we could pull this complex code out into plugins and we could rely on a huge ecosystem of other plug-in authors to do some of the heavy lifting with common things for us.

This plugin architecture is a huge part of Gatsby and what makes it so popular and powerful.

## “What is Gatsby?” Review
So just to briefly review, Gatsby is a static site generator that uses GraphQL to get data, React for templating and it’s got a plugin architecture.

So that is “What is Gatsby?”

## Why Use Gatsby?
Now let’s talk about “Why Use Gatsby?”

In one simple sentence, you use Gatsby for its speed security and improved developer experience.

> Arguably one of the biggest gains that you get with Gatsby, because it is generating a static site, is going to be the speed.

It is going to be way faster than many of the alternatives, even compared to cached sites using WordPress and things like that because that static site is really hard to beat in terms of its speed and performance.

> Also because of the static nature and just shipping HTML files this is going to be inherently more secure.


There `isn’t` a live database to `hack` or `access`. There is not user data that is going to be stored on the server with the Gatsby site. So even `if` somebody were to be able to `hack` the server itself they’re still `only` going to get access to `HTML` files and will be able to do far less damage than they could if they were getting access to for example a WordPress site or had access to the user data or purchasers credit card information and all that kind of stuff.

So we’re gonna have huge `security` gains when we work with Gatsby.

> Finally, the third major gain with Gatsby is improved developer experience.

I’m really glad that this is something important in the `developer community` today. It can be really draining and annoying for developers to work with antiquated stacks.

One of the nice things about working with Gatsby is that you have a `modern` development environment. The tooling is simple and robust. The languages are modern and clean. Overall it’s a really great environment to be working in. That extends also into the community of other developers.

If you are a developer this should be super clear to you and exciting. If you’re not a developer and learning about Gatsby at a high level, remember that this is something you really need to value in your projects: the developers overall experience.

## Gatsby JS is Open Source with a Paid Team
The last thing to remember about all of this is that Gatsby has a solid team open-source community and great documentation.

Gatsby is an open-source project which has some great wins in terms of its ability to grow and people contribute to it. Also it’s free! That’s no small thing.

However, unlike some open-source communities, Gatsby also has a team of professional, paid people that are there to help the open-source project grow and flourish.

This is a great thing if you’re considering investing in a technology that might not have the long term support you probably don’t have to worry about that with Gatsby.

## Gatsby Values Documentation
Additionally, there is great documentation and that is really helpful when working with a tool to know that you’ll be supported in the documentation. The Gatsby team seems to take that seriously and do a great job with it.

## A Quick Review of Gatsby JS
So, all that said let’s just do a quick review here of everything that we’ve learned:

1. Gatsby is a static site generator
2. Under the hood it uses Node, GraphQL and React
3. Its primary benefits are speed security and developer experience
4. Gatsby has a stable and growing community of developers and plug-in authors