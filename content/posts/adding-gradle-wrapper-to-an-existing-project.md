---
title: "Adding Gradle Wrapper to an Existing Project"
date: 2021-10-23T12:54:14+03:00
draft: false
---

Another little one today, I specifically tried to build the vlc-android app myself to fix a song title issue I have.
However, it wasn't building with the error
```
Gradle sync failed: Minimum supported Gradle version is 7.0.2. Current version is 6.8. If using the gradle wrapper, try editing the distributionUrl in /home/ariedov/Projects/vlc-android/gradle/wrapper/gradle-wrapper.properties to gradle-7.0.2-all.zip (5 s 953 ms)
```
but there is no `gradle/*` or `gradlew` included in the repository. That's not how I usually have my repositories, so I did not have an immediate solution to that problem.

A quick google search had the answer. I had to install `gradle` generally to my system first. I have a PopOS installation at the time, so a simple `sudo snap install gradle --classic` helped.

Next, while in the repo directory, I had to add the gradle wrapper for the project by executing:
```
gradle wrapper --gradle-version 7.0.2
```

Voila, project is building without issues, all ready to go.