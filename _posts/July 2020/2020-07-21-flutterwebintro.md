---
layout: post
title:  "Flutter for Web"
categories: [ Web Development ]
date:   2020-07-20 06:00:00 +0530
image: https://flutter.dev/images/Dart-framework-v-browser-framework.png
comments: true
permalink: "/flutter-web-install"
published: true
tags: [ featured ]
---
## What is Flutter Web?

A connected `P`rogressive `W`eb `A`pplication built with Flutter

`Web` support for `Flutter` enables existing mobile-based applications to be packaged as a `PWA` for reach to a broader variety of devices, or to provide a companion `web` experience to an existing app.

In addition to mobile apps, Flutter supports the generation of web content rendered using standards-based web technologies: HTML, CSS and JavaScript. With web support, you can compile existing Flutter code written in Dart into a client experience that can be embedded in the browser and deployed to any web server. You can use all the features of Flutter, and you don’t need a browser plug-in.

**Flutter Solves The Backend & Frontend Problem**

Flutter's `reactive` framework brushes aside the need to get references to the widgets. On the other hand, it facilitates a single language to structure backend. That's why Flutter is the `best` app development `framework` in the `21st century` to be used by `Android developers`.

## How to activate Flutter Web ?
`if you want to install flutter check this` [article].

Run the following commands to use the latest version of the Flutter SDK from the beta channel and enable web support:
{% highlight ruby %}
 $ flutter channel beta
 $ flutter upgrade
 $ flutter config --enable-web
{% endhighlight %}

Once web is enabled, the `flutter devices` command outputs a `Chrome` device that opens the Chrome browser with your app running, and a Web Server that provides the URL serving the app.
{% highlight ruby %}
 flutter devices
2 connected device:

Web Server • web-server • web-javascript • Flutter Tools
Chrome     • chrome     • web-javascript • Google Chrome 81.0.4044.129
{% endhighlight %}

## Create and run
To create a new app that includes web support (in addition to mobile support), run the following commands, substituting `myapp` with the name of your project:
{% highlight ruby %}
 $ flutter create myapp
 $ cd myapp
{% endhighlight %}
To serve your app from `localhost` in Chrome, enter the following from the top of the package:
{% highlight ruby %}
$  flutter run -d chrome
{% endhighlight %}

A release build uses `dart2js` (instead of the `development compiler`) to produce a single JavaScript file `main.dart.js`. You can create a release build using release mode (`flutter run --release`) or by using `flutter build web`. This populates a `build/web` directory with built files, including an assets directory, which need to be served together.

## Add web support to an existing app
To add web support to an existing project, run the following command in a terminal from the root project directory:
{% highlight ruby %}
$  flutter create .
{% endhighlight %}

## Hosting

Check out this [page] to know more about hosting Flutter Web.

[article]: https://naveenjujaray.js.org/flutterinstall
[page]: https://naveenjujaray.js.org/hosting-sites-top-5