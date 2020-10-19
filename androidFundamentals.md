# ANDROID FUNDAMENTALS   
[Home](./README.md)     
[Reference](https://developer.android.com/guide/components/fundamentals) 

Android apps can be written using:

Kotlin
Java
C++

The Android system implements the __principle of least privilege__. That is, each app, by default, has access only to the components that it requires to do its work and no more. This creates a very secure environment in which an app cannot access parts of the system for which it is not given permission. However, there are ways for an app to share data with other apps and for an app to access system services:

There are four different types of app components:

Activities
Services
Broadcast receivers
Content providers


An __activity__ is the entry point for interacting with the user. It represents a single screen with a user interface. 

An activity facilitates the following key interactions between system and app:
* Keeping track of what the user currently cares about (what is on screen) to ensure that the system keeps running the process that is hosting the activity.
* Knowing that previously used processes contain things the user may return to (stopped activities), and thus more highly prioritize keeping those processes around.
* Helping the app handle having its process killed so the user can return to activities with their previous state restored.
* Providing a way for apps to implement user flows between each other, and for the system to coordinate these flows. (The most classic example here being share.)


A __service__ is a general-purpose entry point for keeping an app running in the background for all kinds of reasons. It is a component that runs in the background to perform long-running operations or to perform work for remote processes.  

A service is implemented as a subclass of Service. 




Android SDK Tools

compile code with data and resource files into an APK (Android package).
archive file with .apk suffix
one apk file contains all the contents of an android app
the apk file is used by Android-powered devices to install the app
Android Security Features

OS is a multi-user Linux system, each app is a different user.
By default, the system assigns each app a unique Linux user ID and sets permissions for all the files in an app so that only the user ID assigned can access them.
Each app has its own virtual machine (VM) so the app’s code runs in isolation from other apps.
App Components

activities
entry point for interacting with the user
services
general purpose entry-point for keeping an app running in the background for multiple reasons
broadcast receivers
a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements
content providers
manages a shared set of app data that you can store in:
the file system
a SQLite database
on the web
on any persistent storage location accessible by the app