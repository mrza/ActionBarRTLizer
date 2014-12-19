[![Maven Central](https://maven-badges.herokuapp.com/maven-central/info.semsamot/actionbar-rtlizer/badge.svg?style=flat)](https://maven-badges.herokuapp.com/maven-central/info.semsamot/actionbar-rtlizer)

ActionBar RTLizer (ActionBar RTL Arranger)
================

A library that can RTLize android's `ActionBar`!

It is not a custom `ActionBar` or anything else!
Its only a piece of code that can re-arrange the android's `ActionBar` in RTL direction.

Announcement
================
ActionBarRTLizer v2 is released!  
Fully compatible with API Level 7+ and all issues has been solved!  
Based on a new Amazaing Library -> Rtlize Everything(coming soon)!  

Usage (only 2 simple steps)
================
**1)** Add this line to `build.gradle` file inside your app project folder:
```groovy
dependencies {
    // other stuff
    .
    .
    compile 'info.semsamot:actionbar-rtlizer:2.+@aar'
}
```

**2)** In `onCreateOptionsMenu` method of your activity, before `return` statement, add these lines:

```java
ActionBarRtlizer rtlizer = new ActionBarRtlizer(this);
ViewGroup homeView = (ViewGroup) rtlizer.getHomeView();

RtlizeEverything.rtlize(rtlizer.getActionBarView());

if (rtlizer.getHomeViewContainer() instanceof ViewGroup) {
    RtlizeEverything.rtlize((ViewGroup) rtlizer.getHomeViewContainer());
}

RtlizeEverything.rtlize(homeView);
rtlizer.flipActionBarUpIconIfAvailable(homeView);
```

Then compile your app and enjoy of this awesome RTLization!

Also see this gist for a sample:
https://gist.github.com/semsamot/11fc8d69bdcc0e5cd20a#file-ab_rtlizer_fragment_menu_sample-java

Alternative features
================
You can retrieve `ActionBarView`, `ActionMenuView` and `HomeView` from an instance of `ActionBarRtlizer` class.
Fortunately you can listen for RTLization completed event.

An example of using these features is that you can animate ActionBar menu items. it's so simple! (see the below sample)

```java
Animation rotateAnim = AnimationUtils.loadAnimation(getBaseContext(), R.anim.rotate);
View actionMenuItem = rtlizer.getActionMenuView().findViewById(
        R.id.action_item);
actionMenuItem.setAnimation(rotateAnim);
```

Provided methods for retrieving ActionBar view and its children:

```java
getActionBarView()
getHomeViewContainer() // returns null on lower API versions than 17
getHomeView()
getActionMenuView()
```

Compatibility
================
This library is fully compatible with API Level 7+

Known issues
================
?

Apps using this library
================
If you have interested in using this library in your app, then you may send me your app name, so i can put that on the list and have proud that your app used this library.

Donate
================
With money? **No**

If you like this library, you can make a donation by **clicking** on the **star** in top of this page. Its so simple!

License
================
> Copyright 2014 semsamot

> Licensed under the Apache License, Version 2.0 (the "License");
> you may not use this file except in compliance with the License.
> You may obtain a copy of the License at

>     http://www.apache.org/licenses/LICENSE-2.0

> Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Tags:
action bar rtl, rtl action bar, action bar in rtl, action bar rtl direction, android action bar rtl, action bar rtl arranger, action bar rtlizer, actionbar rtl, rtl actionbar
