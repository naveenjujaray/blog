---
layout: post
title:  "How To Create A GitHub Profile README"
date:   2020-07-12 17:00:00 +0530
categories: [ Jekyll, tutorial ]
image: assets/images/2.jpg
comments: true
permalink: "/readme_github_profile"
published: true
---
GitHub recently released a feature that allows users to create a profile-level README to display prominently on their GitHub profile. This article walksthrough how to access this new feature. 

# Why READMEs?
The GitHub profile-level README feature allows more content than the profile bio, supports markdown which means you can play around with the content more visually (Did someone say GIFs!?) and the README is significantally more visible as it is placed above pinned repositories and takes up as much space above the fold of the webpage as you like.

A solid README is a core-component of well-documented software and often encourages collaboration by sharing helpful context with contributors. In my opinion, a profile-level README seems like a great extension of a convention a lot of GitHub users are already familiar with. If you're looking to make project-level READMEs more awesome and helpful check out [matiassingers/awesome-readme] for resources and examples of compelling READMEs.

# How do I create a profile README?
The profile `README` is created by creating a new repository that’s the same name as your username. For example, my GitHub username is m0nica so I created a new repository with the name naveenjujaray. Note: at the time of this writing, in order to access the profile README feature, the letter-casing must match your GitHub username.

If you already have a project in a repo-named username/username and are interested in setting up a profile-level README, then I recommend either [re-naming that repository] or re-purposing the existing project's README based on what makes the most sense in your particular situation.

- Create a new repository with the same name (including casing) as your GitHub username: https://github.com/new

- Create a README.md file inside the new repo with content (text, GIFs, images, emojis, etc.)

- Commit your fancy new README!

    - If you're on GitHub's web interface you can choose to commit directly to the repo's main branch (i.e., master or main) which will make it immediately visible on your profile.
    - 
- Push changes to GitHub (if you made changes locally i.e., on your computer and not github.com)

![new-repository](/assets/images/5.jpg)

# Fun READMEs
The `GitHub README` profiles are written in Markdown which means you aren't just limited to texts and links, you can include GIFs and images. Need to brush up on Markdown Syntax? [Check out this Markdown Cheatsheet].

![no1](/assets/images/funreadme/no1.jpg)


<blockquote class="twitter-tweet"><p lang="en" dir="ltr">When you&#39;re not a designer so you try code something cool for your <a href="https://twitter.com/github?ref_src=twsrc%5Etfw">@github</a> profile intro. <br><br>Code -&gt; MP4 -&gt; GIF<a href="https://twitter.com/hashtag/Github?src=hash&amp;ref_src=twsrc%5Etfw">#Github</a> <a href="https://twitter.com/hashtag/JavaScript?src=hash&amp;ref_src=twsrc%5Etfw">#JavaScript</a> <a href="https://t.co/gQEQH3l0DG">pic.twitter.com/gQEQH3l0DG</a></p>&mdash; Cyris ⭐️ (@sudo_overflow) <a href="https://twitter.com/sudo_overflow/status/1281146411736694784?ref_src=twsrc%5Etfw">July 9, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Is this how we suppose use github&#39;s readme? <a href="https://t.co/XvLvCUC6iD">pic.twitter.com/XvLvCUC6iD</a></p>&mdash; Pouya (@Saadeghi) <a href="https://twitter.com/Saadeghi/status/1281111778290786310?ref_src=twsrc%5Etfw">July 9, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

If you're really ambitious you can use [GitHub actions] or other automation like bdougieYO or simonw to dynamically pull data into your `README`:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Check it out. I made MySpace but on <a href="https://twitter.com/github?ref_src=twsrc%5Etfw">@github</a>.<a href="https://t.co/p4DWP4DxRR">https://t.co/p4DWP4DxRR</a> - My list is power by a GitHub Action workflow 😏 <a href="https://t.co/PN80mFCqOE">pic.twitter.com/PN80mFCqOE</a></p>&mdash; Brian Douglas (@bdougieYO) <a href="https://twitter.com/bdougieYO/status/1281699715466199040?ref_src=twsrc%5Etfw">July 10, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


![no2](/assets/images/funreadme/no2.jfif)

I'm a huge proponent that folks should maintain a website they have complete ownership over (even if it's a no-code website solution) but this is tempting...

![no3](/assets/images/funreadme/no3.jfif)

![no4](/assets/images/funreadme/no4.jpg)

I've been inspired by the creative `READMEs` I've seen so far and am looking forward to seeing all kinds of profiles in the upcoming months.

[matiassingers/awesome-readme]: https://github.com/matiassingers/awesome-readme
[re-naming that repository]: https://docs.github.com/en/github/administering-a-repository/renaming-a-repository
[Check out this Markdown Cheatsheet]: https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf
[GitHub actions]: https://github.com/features/actions