# Trabalho1-install-tools

Two activities for today:
- Download and Install Android Studio
- Download and Install Android SDK

After you finish the two activities, please, upload a screenshot of the installation folders for the both softwares.
Next you will need to take a screenshot o your Android Studio up and running 

## DEADLINE is Tomorrow at 8pm. no Excuses
### Android Developer Website

Android Studio is distributed freely by Google, and the most up-to-date reference for installing and using the Android Studio software can be found on the Android developer website:

[http://developer.android.com/sdk/index.html](http://developer.android.com/sdk/index.html)

Android Studio is available on the Windows, MacOS, and Linux operating systems.

### [](https://github.com/ftctechnh/ftc_app/wiki/Installing-Android-Studio#system-requirements)System Requirements

Before you download and install the Android Studio you should first check the list of system requirements on the Android developer’s website to verify that your system satisfies the list of minimum requirements:

[http://developer.android.com/sdk/index.html#Requirements](http://developer.android.com/sdk/index.html#Requirements)

### [](https://github.com/ftctechnh/ftc_app/wiki/Installing-Android-Studio#java-development-kit)Java Development Kit

Earlier versions of Android Studio used to require that the user install the Java Development Kit software separately. Current versions of Android Studio incorporate the Java development software as part of the entire install package. It is no longer necessary (or recommended) to install the Java Development Kit separately.

### [](https://github.com/ftctechnh/ftc_app/wiki/Installing-Android-Studio#downloading-and-installing-android-studio)Downloading and Installing Android Studio

Once you have verified that your laptop satisfies the minimum system requirements, you can go to the Android developer’s website to download and install Android Studio:

[https://developer.android.com/studio/index.html](https://developer.android.com/studio/index.html)

Click on the green “DOWNLOAD ANDROID STUDIO” button to start the download process.

![](https://github.com/FIRST-Tech-Challenge/WikiSupport/raw/master/ftc_app/images/AndroidStudio/DownloadAndroidStudio.jpg)

Accept the license terms and then push the blue “DOWNLOAD ANDROID STUDIO” button to download the software.

![](https://github.com/FIRST-Tech-Challenge/WikiSupport/raw/master/ftc_app/images/AndroidStudio/AndroidStudioWelcomeSetup.jpg)

Once the setup package has downloaded, launch the application and follow the on-screen instructions to install Android Studio.

# Installing Android SDK Tools



The Android software development kit (SDK) includes different components, including SDK Tools, Build Tools, and Platform Tools. The SDK Tools primarily includes the stock Android emulator, [hierarchy viewer](https://developer.android.com/studio/profile/hierarchy-viewer.html), [SDK manager](https://developer.android.com/studio/intro/update.html), and [ProGuard](https://github.com/codepath/android_guides/wiki/Configuring-ProGuard). The Build Tools primarily include `aapt` (Android packaging tool to create `.APK`), `dx` (Android tool that converts .java files to `.dex` files). Platform Tools include the [Android debug shell](https://developer.android.com/studio/command-line/adb.html), [sqlite3](https://developer.android.com/studio/command-line/sqlite3.html) and [Systrace](https://developer.android.com/studio/profile/systrace-commandline.html).

The Android SDK can be installed automatically using the latest version of Gradle or downloading the Android SDK manually in several different ways. Below is an overview of all different approaches.

## [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-the-android-sdk-automated-way)Installing the Android SDK (Automated Way)

Gradle 2.2.0 now supports downloading automatically dependencies. Make sure to [upgrade](https://github.com/codepath/android_guides/wiki/Getting-Started-with-Gradle#upgrading-gradle) to the latest Gradle version. The [Gradle plugin](https://github.com/JakeWharton/sdk-manager-plugin) to manage dependencies is now deprecated.

### [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-for-ubuntu-linux)Installing for Ubuntu Linux

If you are using Ubuntu 15.04 or 15.10, make sure to install the following packages. Otherwise, you may notice `No such file or directory` when running trying to execute the `aapt` program that is part of the Android SDK toolset:

sudo apt-get install libc6-dev-i386 lib32z1 default-jdk

## [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-the-android-sdk-via-homebrew)Installing the Android SDK (via Homebrew)

Assuming you have OS X running, you can use Homebrew to install the Android SDK.

1.  [Install Homebrew](http://brew.sh/) - package manager for OSX
2.  run

```
brew tap caskroom/cask
brew cask install android-sdk

```

This will install the Android SDK tools in `/usr/local/Cellar/android-sdk/<version number>`

## [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-the-android-sdk-manual-way)Installing the Android SDK (Manual Way)

You will need to download the Android SDK without Android Studio bundled. Go to [Android SDK](http://developer.android.com/sdk/index.html) and navigate to the **SDK Tools Only** section. Copy the URL for the download that's appropriate for your build machine OS.

![List of Android SDK downloads from developers.android.com](https://camo.githubusercontent.com/6d3acd1a3052e25b1784815e0197b177ca76f3a6/68747470733a2f2f696d6775722e636f6d2f495243574859372e706e67)

Use `wget` with the correct SDK URL:

```
$ wget https://dl.google.com/android/repository/tools_r25.2.3-macosx.zip

```

Unzip and place the contents within your home directory. The directory names can be anything you like, but save the files in somewhere easy to find (i.e. ~/android-sdk).

Run the `sdkmanager` tool:

```
$ tools/bin/sdkmanager --update
$ tools/bin/sdkmanager "platforms;android-25" "build-tools;25.0.2" "extras;google;m2repository" "extras;android;m2repository"
$ tools/bin/sdkmanager --licenses

```

![Directory structure on the build server](https://camo.githubusercontent.com/477e0ed70e0652215e04c4203397a135566b7519/68747470733a2f2f646c2e64726f70626f7875736572636f6e74656e742e636f6d2f752f31303830383636332f677261646c655f6a656e6b696e735f616e64726f69642f6469726563746f726965735f6f6e5f6275696c645f7365727665722e706e67)

Now it's time to set your build environment's `PATH` variable and other variables that will be use to locate Android.

Edit your `.bash_profile` file. If you're not using bash, edit the right config file for your environment.

```
# Android 
export ANDROID_SDK_ROOT=/Users/ciandroid/android-sdk-macosx
export PATH=$PATH:$ANDROID_SDK_ROOT/tools

```

Save and quit. Reload `.bash_profile`:

```
$ source ~/.bash_profile

```

### [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-via-the-gui)Installing via the GUI

At the prompt, type `android` and hit Enter to launch the Android SDK Manager in a window. If this doesn't work, your `PATH` variable has not been set up with the Android SDK location.

![Android SDK manager on build machine](https://raw.githubusercontent.com/codepath/android_guides/master/images/intellij_idea_android_sdk_manager.png)

You will want to install the same Android SDK packages on your build machine as you did to get Gradle running locally. Before you begin, take a look at the `build.gradle` file in your project.

#### [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#packages-to-install)Packages to install

Here are the SDK package names you'll definitely wish to select:

-   `Tools > Android SDK Tools`
-   `Tools > Android SDK Platform-tools`
-   `Tools > Android SDK Build-tools`
-   One version of the Android Platform. E.g., `Android 5.1.1 (API 22)`. It should be the one you named in the `android: compileSdkVersion` section of your `build.gradle` file.

You will also want to download the extras:

-   Android Support Repository
-   Android Support Library

Note: Choose the Android SDK Build-tools for the version of Android that you listed in the `build.gradle` file as the `android: buildToolsVersion` target. If your `build.gradle` says

    android {
        buildToolsVersion '21'
        ...
    }

then make sure to download that API version in the Android SDK Manager.

#### [](https://github.com/codepath/android_guides/wiki/Installing-Android-SDK-Tools#installing-via-the-command-line)Installing via the Command Line

You can also download the SDK packages using the command line with the `--no-ui` parameter.

```
android update sdk --no-ui --all

```

If you want to be selective about installing, you can use `android list` to view all the packages and apply the `--filter` option for selective installs:

```
sudo android update sdk --no-ui --filter platform-tools,tools

```

If you decide to be selective about which packages to be installed, make sure to include the extra Android Maven repository. Otherwise, you may not be able to use the latest [support design library](https://github.com/codepath/android_guides/wiki/Design-Support-Library).

```
android update sdk --no-ui --all --filter extra-android-m2repository     

```

There is currently no filter to install the build tools directly. See this [ticket](https://code.google.com/p/android/issues/detail?id=78765) for more information.


