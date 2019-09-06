---
layout: post
title: Setting Up Android SDK in IntelliJ IDEA on macOS
---

Condensed instructions on how to install and add the latest Android SDK to IntelliJ IDE on macOS

## Initial situation

You may have already been using [IntelliJ IDEA](https://www.jetbrains.com/idea/ "IntelliJ IDEA: The Java IDE for professional developers by JetBrains") for a while, done some Java development and do not want to install [Android Studio](https://developer.android.com/studio/index.html "The Official IDE for Android") additionally, as all of its features are already available in IntelliJ. Note also that IntelliJ IDEA Ultimate features are not available in Android Studio. Lastly, you have already installed [homebrew](https://brew.sh "The missing package manager for macOS") and XCode command line tools. Oh, and you're a user of macOS.

## Instructions

Use homebrew to install the Android dev tools. Check if homebrew and the formulae are up to date by running

```
  $ brew update
```

in your terminal.

Then, execute the commands
```
  $ brew install ant
  $ brew install maven
  $ brew install gradle
  $ brew cask install android-sdk
  $ brew cask install android-ndk
```

At this point you can add the Android SDK to your platform settings in IntelliJ. Before that, you need to create the "Platforms" folder, otherwise IntelliJ can't detect the Android SDK and will throw "The selected directory is not a valid home for Android SDK" error message. 

Check the availability of the `platforms;android-<VERSION>` package

```
  $ sdkmanager --list
```

and install it by running 

```
  $ sdkmanager "platforms;android-<VERSION>"
```
where `<VERSION>` is the version that you wish to install. 

In the IntelliJ Welcome Screen, go to Configure > Project Defaults > Project Structure > Platform Settings > SDKs. Click `+` to add a new SDK. A file chooser dialog should pop up. Use <kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>.</kbd> to reveal all hidden folders. **You will need to do that even if you have already enabled showing all files for Finder**. This step is necessary in order to navigate into the hidden `/usr/` directory where your Android SDK is located. 

Lastly, navigate to the `/usr/local/Caskroom/android-sdk/<VERSION>` directory and choose it. In this case, `<VERSION>` references the version that was installed by Homebrew-Cask, 

Apply changes and then you're good to go :thumbsup:.

## Resources
* [Deprecated setup instructions by Patrick Hammond](https://gist.github.com/patrickhammond/4ddbe49a67e5eb1b9c03)
* <https://stackoverflow.com/questions/43433542/stuck-at-android-repositories-cfg-could-not-be-loaded>
* <https://stackoverflow.com/questions/44840056/the-selected-directory-is-not-a-valid-home-for-android-sdk-intellij-2017>