---
layout: post
title:  "Adaptive Theme on Flutter"
date:   2020-09-01 09:41:03 +0530
categories: [ Flutter, Dart ]
image: assets/images/funreadme/adaptive_theme.png
comments: true
permalink: "/flutter-adaptive-theme"
published: true
---
# Adaptive Theme on Flutter

Easiest way to add support for light and dark theme in your flutter app. It allows to manually set light or dark theme and also lets you define themes based on the system (Works for Android only for now). It also persists the theme modes changes across app restarts.

### Installation
add following dependency to your `pubspec.yaml`
```
dependencies:
  adaptive_theme: ^1.0.0
```
### Usage
You need to wrap your `MaterialApp` with `AdaptiveTheme` in order to apply themes
```
import 'package:adaptive_theme/adaptive_theme.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return AdaptiveTheme(
      light: ThemeData(
        brightness: Brightness.light,
        primarySwatch: Colors.red,
        accentColor: Colors.amber,
      ),
      dark: ThemeData(
        brightness: Brightness.dark,
        primarySwatch: Colors.red,
        accentColor: Colors.amber,
      ),
      initial: AdaptiveThemeMode.light,
      builder: (theme, darkTheme) => MaterialApp(
        title: 'Adaptive Theme Demo',
        theme: theme,
        darkTheme: darkTheme,
        home: MyHomePage(),
      ),
    );
  }
}
```
### Changing Theme Mode
Now that you have initialized your app as mentioned above. It's very easy and straight forward to change your theme modes: **light to dark, dark to light or to system default.**
```
// sets theme mode to dark
AdaptiveTheme.of(context).setDark();

// sets theme mode to light
AdaptiveTheme.of(context).setLight();

// sets theme mode to system default
AdaptiveTheme.of(context).setSystem();
```
### Ceveats
Non-Persist theme changes
> This is only useful in scenarios where you load your themes dynamically from network in the splash screen or some initial screens of the app. Please note that AdaptiveTheme does not persist the themes, it only persists the theme modes(light/dark/system). Any changes made to the provided themes won't be persisted and you will have to do the same changes at the time of the initialization if you want them to apply every time app is opened. e.g changing the accent color.

Using SharedPreferences

> This package uses sharedpreferences plugin internally to persist theme mode changes. If your app uses sharedpreferences which might be the case all the time, clearing your sharedpreferences at the time of logging out or signing out might clear these preferences too. Be careful not to clear these preferences if you want it to be persisted.
```
AdaptiveTheme.prefKey
```
You can use above key to exclude it while clearing the all the preferences.

Or you can call `AdaptiveTheme.persist()` method after clearing the preferences to make it persistable again as shown below.
```
final prefs = await SharedPreferences.getInstance();
await pref.clear();
AdaptiveTheme.persist();
```
for live example of `adaptive_theme` : [click here](https://developerfolio.web.app)

for more check this [out](https://pub.dev/packages/adaptive_theme)