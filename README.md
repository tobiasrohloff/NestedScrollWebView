# NestedScrollWebView for Android

A [`WebView`][1] that implements [`NestedScrollingChild`][2], in order to use it with [`CoordinatorLayout`][3] and [`AppBarLayout`][4] from the [Android Design Support Library][5]. This is necessary since embedding a regular [`WebView`][1] in a [`NestedScrollView`][6] causes height [issues](https://code.google.com/p/android/issues/detail?id=198965#c10) (e.g. infinite height, tested with `design:23.1.1`).

This is just a workaround, until Google will hopefully fix it.

The code is based on [this][7] and [this][8].

## Setup Instructions

Set up the project dependencies. To use this library in your project, follow these steps:

 * In the root of your application's project add the library as a git submodule:
```shell
git submodule add https://github.com/rhlff/NestedScrollWebView
```
 * In the root of your application's project edit the file "settings.gradle" and add the following lines:
```shell
include ':NestedScrollWebView:lib'
project(':NestedScrollWebView').projectDir = new File('/NestedScrollWebView')
```
 * In your application's main module (usually called "app"), edit your build.gradle to add a new dependency:
```shell
 dependencies {
    ...
    compile project(':NestedScrollWebView:lib')
 }
```

Now your project is ready to use this library.

To update the library, follow these steps:
* From the root of your application's project change directory to the library:
```shell
cd NestedScrollWebView
```
* Pull the last changes:
```shell
git pull origin master
```

Now the library is up to date.

## Usage

In your layout.xml include the following:

```xml
<com.tobiasrohloff.view.NestedScrollWebView
            android:id="@+id/webView"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />
```

## License

<pre>
Copyright (C) 2016 Tobias Rohloff

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
</pre>

[1]: http://developer.android.com/reference/android/webkit/WebView.html
[2]: http://developer.android.com/reference/android/support/v4/view/NestedScrollingChild.html
[3]: http://developer.android.com/reference/android/support/design/widget/CoordinatorLayout.html
[4]: http://developer.android.com/reference/android/support/design/widget/AppBarLayout.html
[5]: http://developer.android.com/tools/support-library/features.html#design
[6]: http://developer.android.com/reference/android/support/v4/widget/NestedScrollView.html
[7]: https://android.googlesource.com/platform/frameworks/support/+/refs/heads/master/v4/java/android/support/v4/widget/NestedScrollView.java
[8]: https://github.com/llfer2006/NestLayout/blob/master/library/src/main/java/com/llf/nestlayout/library/NestWebView.java