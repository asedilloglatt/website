---
title: Add Flutter to an existing app
short-title: Add to app
description: Adding Flutter as a library to an existing Android or iOS app.
---

## Add-to-app

It's sometimes not practical to rewrite your entire application in
Flutter all at once. For those situations,
Flutter can be integrated into your existing
application piecemeal, as a library or module.
That module can then be imported into your Android or iOS
(currently supported platforms) app to render a part of your
app's UI in Flutter. Or, just to run shared Dart logic.

In a few steps, you can bring the productivity and the expressiveness of
Flutter into your own app.

The `add-to-app` feature supports integrating multiple instances of any screen size.
This can help scenarios such as a hybrid navigation stack with mixed
native and Flutter screens, or a page with multiple partial-screen Flutter
views.

Having multiple Flutter instances allows each instance to maintain
independent application and UI state while using minimal
memory resources. See more in the [multiple Flutters][] page.

## Supported features

### Add to Android applications

{% include docs/app-figure.md image="development/add-to-app/android-overview.gif" alt="Add-to-app steps on Android" %}

* Auto-build and import the Flutter module by adding a
  Flutter SDK hook to your Gradle script.
* Build your Flutter module into a generic
  [Android Archive (AAR)][] for integration into your
  own build system and for better Jetifier interoperability
  with AndroidX.
* [`FlutterEngine`][java-engine] API for starting and persisting
  your Flutter environment independently of attaching a
  [`FlutterActivity`][]/[`FlutterFragment`][] etc.
* Android Studio Android/Flutter co-editing and module
  creation/import wizard.
* Java and Kotlin host apps are supported.
* Flutter modules can use [Flutter plugins][] to interact
  with the platform.
* Support for Flutter debugging and stateful hot reload by
  using `flutter attach` from IDEs or the command line to
  connect to an app that contains Flutter.

### Add to iOS applications

{% include docs/app-figure.md image="development/add-to-app/ios-overview.gif" alt="Add-to-app steps on iOS" %}

* Auto-build and import the Flutter module by adding a Flutter
  SDK hook to your CocoaPods and to your Xcode build phase.
* Build your Flutter module into a generic [iOS Framework][]
  for integration into your own build system.
* [`FlutterEngine`][ios-engine] API for starting and persisting
  your Flutter environment independently of attaching a
  [`FlutterViewController`][].
* Objective-C and Swift host apps supported.
* Flutter modules can use [Flutter plugins][] to interact
  with the platform.
* Support for Flutter debugging and stateful hot reload by
  using `flutter attach` from IDEs or the command line to
  connect to an app that contains Flutter.

See our [add-to-app GitHub Samples repository][]
for sample projects in Android and iOS that import
a Flutter module for UI.

## Get started

To get started, see our project integration guide for
Android and iOS:

<div class="card-deck mb-8">
  <a class="card" href="{{site.url}}/add-to-app/android/project-setup">
    <div class="card-body">
      <header class="card-title text-center m-0">
        Android
      </header>
    </div>
  </a>
  <a class="card" href="{{site.url}}/add-to-app/ios/project-setup">
    <div class="card-body">
      <header class="card-title text-center m-0">
        iOS
      </header>
    </div>
  </a>
</div>

## API usage

After Flutter is integrated into your project,
see our API usage guides at the following links:

<div class="card-deck mb-8">
  <a class="card" href="{{site.url}}/add-to-app/android/add-flutter-screen">
    <div class="card-body">
      <header class="card-title text-center m-0">
        Android
      </header>
    </div>
  </a>
  <a class="card" href="{{site.url}}/add-to-app/ios/add-flutter-screen">
    <div class="card-body">
      <header class="card-title text-center m-0">
        iOS
      </header>
    </div>
  </a>
</div>

## Limitations

* Packing multiple Flutter libraries into an
  application isn't supported.
* Plugins that don't support `FlutterPlugin` might have unexpected
  behaviors if they make assumptions that are untenable in add-to-app
  (such as assuming that a Flutter `Activity` is always present).
* On Android, the Flutter module only supports AndroidX applications.

[add-to-app GitHub Samples repository]: {{site.github}}/flutter/samples/tree/main/add_to_app
[Android Archive (AAR)]: {{site.android-dev}}/studio/projects/android-library
[Flutter plugins]: {{site.pub}}/flutter
[`FlutterActivity`]: {{site.api}}/javadoc/io/flutter/embedding/android/FlutterActivity.html
[java-engine]: {{site.api}}/javadoc/io/flutter/embedding/engine/FlutterEngine.html
[ios-engine]: {{site.api}}/objcdoc/Classes/FlutterEngine.html
[FlutterFire]: {{site.github}}/firebase/flutterfire/tree/master/packages
[`FlutterFragment`]: {{site.api}}/javadoc/io/flutter/embedding/android/FlutterFragment.html
[`FlutterPlugin`]: {{site.api}}/javadoc/io/flutter/embedding/engine/plugins/FlutterPlugin.html
[`FlutterViewController`]: {{site.api}}/objcdoc/Classes/FlutterViewController.html
[iOS Framework]: {{site.apple-dev}}/library/archive/documentation/MacOSX/Conceptual/BPFrameworks/Concepts/WhatAreFrameworks.html
[maintained by the Flutter team]: {{site.repo.packages}}/tree/main/packages
[multiple Flutters]: {{site.url}}/add-to-app/multiple-flutters
