---
layout: post
title:  "Create your own blog easily with Gatsby"
categories: [ Web Development, Hosting ]
date:   2020-07-14 12:23:00 +0530
image: assets/images/firebase/8.png
comments: true
permalink: "/gatsby-intro"
published: true
---
[Gatsby] is a Static site generator. (There are so many kinds of generator like Jekyll(Ruby), Hexo(Node.js), Hugo(Go), etc.) Gatsby support PWA(Progressive Web App), Hot reloading, SSR(Server Side Rendering).

You can see more detailed in [this link].
## Install Gatsby CLI and Gatsby Starter
{% highlight ruby %}
$ npm i -g gatsby-cli
$ gatsby new <<BLOG_NAME>> https://github.com/wonism/gatsby-advanced-blog
$ cd <<BLOG_NAME>>
$ npm run dev
{% endhighlight %}
## Basic structure of project
The project has the following structure.
{% highlight ruby %}
src/
├── components
│   ├── ... # Many of shared sections
│   └── layout.jsx # general layout for page
├── constants
├── containers # to connect states to react component
├── html.jsx # page template for page
├── pages # pages of your web site
│   ├── 404.jsx
│   └── index.js
├── postComponents # react application that will be added in page
│   └── ...
├── resources # asset files
│   └── images
├── store # to use redux
│   ├── ...
│   └── index.js
├── templates # template for creating page with file system
│   └── ...
└── utils # utilities
    └── ...
{% endhighlight %}
## Create a post
{% highlight ruby %}
$ mkdir src/pages/<<DIRECTORY_NAME>>
$ touch src/pages/<<DIRECTORY_NAME>>/index.md
{% endhighlight %}
These markdown files are referred by the gatsby-source-filesystem and converted to HTML files by gatsby-transformer-remark.

These are called at build time. You can check this createPages in gatsby-node.js.

## Caution
There is a .sample.md file in <<PROJECT_ROOT>>/src/pages.
If you delete this file, you can not get category, image, etc. in frontmatter of GraphQL query.

The .sample.md file serves as the dummy data and creates custom frontmatter fields.

## The basic components of a markdown file
{% highlight ruby %}
---
path: "/hello-world/"
category: "Sample"
tags: ["tag", "should", "be", "array"]
title: "Hello, World!"
date: "2018-08-15T00:00:00.000Z"
summary: "You can create your own blog with Gatsby!"
---

Content of this page
{% endhighlight %}
- path is a **required** attribute to create a page. It must be unique.
- category allows you to create category pages and access to pages like `/categories/<<CATEGORY_NAME>>/<<PAGE_NUMBER>>`.
- tags allows you to create tag pages and access to pages like `/tags/<<TAG_NAME>>/<<PAGE_NUMBER>>`.
- As you can see the name oof property. `title` is the title of the page, and `summary` is a summary of the page.
- date is the date the post was created, and posts are sorted based on it.

(You can more detailed information about the formatting in [gray-matter].)

Those will be called by query in _src/templates/Post.jsx._ and you can run the query directly on `http://localhost:8000/___graphql`

## Add image into post
{% highlight ruby %}
images: ["(<<src/resources/>>)PATH_TO/IMAGE"]
{% endhighlight %}
Use an absolute path including _http://_ or _https://_. or use a relative path relative to src/resources.
(__On line 145 ofcomponents/Post/index.jsx__, the image is imported via __IF CONDITION ? <<image>> : '<<src/resources/${image}>>'__)
## Add react application into post
{% highlight ruby %}
---
path: "/inject-app/"
category: "Sample"
tags: ["tag", "must", "be", "array"]
title: "Injecting React application"
date: "2018-08-15T00:00:00.000Z"
summary: "You can inject react application into post"
components: [{
  rootId: 'sample-component', # <div id="sample-component"></div> must be in contents
  fileName: 'sample', # this will render src/postComponents/sample/index.jsx
}]
---

1. ...

<div id="sample-component"></div>

2. ...
{% endhighlight %}
## Put an object in the array. Object has to include the path to the file of the react application that is to be added and the ID of the tag to be rendered.

Then, in the middle of the article, add the tag with this ID where you want to insert the react application.

## Add tweet into post
{% highlight ruby %}
---
path: "/inject-tweet/"
category: "Sample"
tags: ["tag", "must", "be", "array"]
title: "Injecting Tweet"
date: "2018-08-15T00:00:00.000Z"
summary: "You can inject tweet into post"
tweets: [{
  rootId: 'sample-tweet', # <div id="sample-tweet"></div> must be in contents
  userId: 'twitter', # twitter user id
  tweetId: '977557540199456775', # tweet id
}]
---

1. ...

<div id="sample-tweet"></div>

2. ...
{% endhighlight %}
Put an object in the array. Object has to include the tweet's ID and the author or the tweet and the ID of the tag to be rendered.

You can use it as you added the react application.

### Add codes into post
If you write the three back quote before and after the codes that you want to highlight, It will be highlighted by `gatsby-remark-prismjs`.

## Add portfolios
{% highlight ruby %}
$ mkdir src/resources/<<DIRECTORY_NAME>>
$ touch src/resources/<<DIRECTORY_NAME>>/index.md
{% endhighlight %}
{% highlight ruby %}
---
type: "portfolio"
title: "Gatsby Advanced Blog"
date: "2018-08-15T00:00:00.000Z"
path: "/portfolios/portfolio-1/"
images: [
  "test-1/1.png",
  "test-1/2.png",
]
---

# Gatsby Advanced Blog

## What I did
- Develop Gatsby Advanced Blog

## Libraries / Tools
- ReactJS
- Redux
- Redux saga
- ...

[Go to Web Site →](https://github.com/wonism/gatsby-advanced-blog)

{% endhighlight %}
- path is a **required** attribute to create a page. It must be unique.
- type is a value that allows you to specify the format of the page, in this case it should be `portfolio`.
- `title` is the title of the portfolio.
- `images` are the images you want to attach to the portfolio and have the same value as the post's. Images are rendered in the order they were added to the array.
- Portfolios are sorted based on the data. Give a bigger value to the portfolio to show first.

Portfolios will be shown one the portfolio page. and if there are more than 4, they will be shown on the home page.

(You can see it in __src/components/Home__ and modify how it is rendered.)
## Add resume
{% highlight ruby %}
---
type: "resume"
title: "Resume"
date: "2000-01-01T00:00:00.000Z"
path: "/resume/"
---

## Experience
- Engineer at OOO ∙ 2000. 01 ~ Present
  - Develop something
  - Maintain something

## Education
- B.S. in Computer Science Engineering at OOO
  - 2000. 01 ~ 2000. 01

## Projects
- Gatsby Advanced Blog (https://github.com/wonism/gatsby-advanced-blog) ∙ 2000. 01 ~ Present
  - Integrate Redux
    - Use Redux, Redux Saga, Reselect...

## Skills
- JavaScript
  - ES2015+
  - ReactJS
  - Lodash
- CSS
  - SASS
  - Less
{% endhighlight %}
- path is a **required** attribute to create a page. It must be unique.
- type is a value that allows you to specify the format of the page, in this case it should be `portfolio`.
## Other features
- On the right side of the GNB, you can search posts by title, summary, tag, category, etc. of the post.
- When you add codes in markdown, a button will be created automatically. If user clicks the button, user can copy the codes.
## Deployment
You can build the application with npm run build.
Then you can distribute it where you want. You can see this article on this [link].

[Gatsby]: https://www.gatsbyjs.org/
[this link]: https://www.gatsbyjs.org/features/
[gray-matter]: https://github.com/jonschlinkert/gray-matter
[link]: https://naveenjujaray.js.org/hosting-sites-top-5