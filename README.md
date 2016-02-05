# NestedScrollWebView for Android

A [`WebView`][1] that implements [`NestedScrollingChild`][2], in order to use it with [`CoordinatorLayout`][3] and [`AppBarLayout`][4] from the [Android Design Support Library][5]. This is necessary since embedding a regular [`WebView`][1] in a [`NestedScrollView`][6] causes height [issues](https://code.google.com/p/android/issues/detail?id=198965#c10) (e.g. infinite height, tested with `design:23.1.1`).

This is just a workaround, until Google will hopefully will fix it.

The code is based on [this][7] and [this][8].

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