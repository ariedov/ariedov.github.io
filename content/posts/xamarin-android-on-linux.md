---
title: "Xamarin.Android on Linux"
date: 2021-10-15T12:50:01+03:00
draft: false
---

### The IDE

First things first - Jetbrains. Rider is required, there is no other tool available for writing Xamarin code on Linux. Grab it here https://www.jetbrains.com/rider/

Make sure to install `Xamarin.Android` support plugin. The installation guide will also have that option available.

### C# on Linux

Next is mono - the layer which allows provides necessary tools to build C# code on Linux and Mac. 
https://www.mono-project.com/

Now the tricky stuff, installing Xamarin.Android. There is no fancy website with installation guides, just an appcenter project with build artifacts. It was Jenkins before that.  https://dev.azure.com/xamarin/public/_build/results?buildid=43659&view=artifacts&pathAsName=false&type=publishedArtifacts

Set it up in Rider

![Setup mono in Rider](/images/xamarin_android_on_linux/setup_mono_rider.png)

### Android Tools

Of course, to run and build Android apps you'd need the Android SDK. It might be installed together with Android Studio or headless from here Of course, to run and build Android apps you'd need the Android SDK. It might be installed together with Android Studio or headless from here https://developer.android.com/studio
#downloads

Don't forget to install Android NDK from the SDK Manager.

Also Java Development Kit (JDK) is crucial, as of 2021 Java 11 is preferred.

Set it up in Rider settings

![Setup Android SDK in Rider](/images/xamarin_android_on_linux/setup_android_sdk_rider.png)

### NuGet

At this point, almost everything is ready, but one crucial tool is required - NuGet to get your dependencies. The installation guide can be found here https://docs.microsoft.com/en-us/nuget/install-nuget-client-tools#nugetexe-cli

In the `.nuget/NuGet.targets` file you will need to specify the nuget location by changing it to something like that

![Setup NuGet in Rider](/images/xamarin_android_on_linux/setup_nuget_in_project.png)

And with some luck, that should allow for your `Xamarin.Android` development joy on Linux. Enjoy.