CWAC AdapterWrapper: Adding Bits o' Functionality
=================================================

Android comes with a few "wrapper" classes, like `CursorWrapper`,
that make it relatively easy for you to add just a bit of
functionality to an existing object. The wrapper delegates
all behaviors to the wrapped object; you just override the
specific behaviors you need. This works well in cases where
there are many possible underlying implementations, so you
could not robustly accomplish these ends by subclassing.

Android lacks such a wrapper for `ListAdapter`, though. There
is a `WrappedListAdapter` entry in the SDK, but it is an interface,
not an implementation.

So, CWAC offers an `AdapterWrapper` to fill this void.

By itself, it is not terribly interesting. However, other CWAC
projects take advantage of it.

This Android library project is 
[available as a JAR](https://github.com/commonsguy/cwac-adapter/releases)
or as an artifact for use with Gradle. To use that, add the following
blocks to your `build.gradle` file:

```groovy
repositories {
    maven {
        url "https://repo.commonsware.com.s3.amazonaws.com"
    }
}

dependencies {
    compile 'com.commonsware.cwac:adapter:1.0.+'
}
```

Or, if you cannot use SSL, use `http://repo.commonsware.com` for the repository
URL.

NOTE: The JAR name, as of v1.0.2, has a `cwac-` prefix, to help distinguish it from other JARs.

Usage
-----
Just extend `AdapterWrapper` and override whatever adapter-related
methods you wish. By default, all adapter methods delegate to the
wrapped adapter. Your code can get at the wrapped adapter by
calling `getWrappedAdapter()`.

Dependencies
------------
None at present.

Version
-------
This is version v1.0.2 of this module. And there was much rejoicing.

Demo
----
There is no demo project.

License
-------
The code in this project is licensed under the Apache
Software License 2.0, per the terms of the included LICENSE
file.

Questions
---------
If you have questions regarding the use of this code, please post a question
on [StackOverflow](http://stackoverflow.com/questions/ask) tagged with
`commonsware-cwac` and `android` after [searching to see if there already is an answer](https://stackoverflow.com/search?q=[commonsware-cwac]+adapterwrapper). Be sure to indicate
what CWAC module you are having issues with, and be sure to include source code 
and stack traces if you are encountering crashes.

If you have encountered what is clearly a bug, please post an [issue](https://github.com/commonsguy/cwac-adapter/issues). Be certain to include complete steps
for reproducing the issue.

Do not ask for help via Twitter.

Release Notes
-------------
- v1.0.2: updated Gradle, fixed manifest for manifest merging, added `cwac-` prefix to JAR
- v1.0.1: added Gradle build files and published AAR
- v1.0.0: made this the official 1.0 release
- v0.4.0: converted to Android library project

Who Made This?
--------------
<a href="http://commonsware.com">![CommonsWare](http://commonsware.com/images/logo.png)</a>

[endless]: http://github.com/commonsguy/cwac-endless/tree/master
