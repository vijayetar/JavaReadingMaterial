# ANDROID FUNDAMENTALS   
[Home](./README.md)     
[Fundamentals](https://developer.android.com/guide/components/fundamentals)   
[SharedReferences](https://developer.android.com/training/data-storage/shared-preferences)  
[Tasks and BackStack](https://developer.android.com/guide/components/activities/tasks-and-back-stack)    

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

__Broadcast receivers__ are a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements

__Content providers__ manages a shared set of app data that you can store in:
the file system a SQLite database on the web on any persistent storage location accessible by the app

## Shared Preferences  

You can create a new shared preference file or access an existing one by calling one of these methods:

* getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.  
* getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.

```
Context context = getActivity();
SharedPreferences sharedPref = context.getSharedPreferences(
        getString(R.string.preference_file_key), Context.MODE_PRIVATE);
```
If you're using the SharedPreferences API to save app settings, you should instead use getDefaultSharedPreferences()  

If you need just one sharedpreference file:
```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
```
__Write__ to shared preference:
```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPref.edit();
editor.putInt(getString(R.string.saved_high_score_key), newHighScore);
editor.apply();
```
__Read__ from shared preference:
```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
int defaultValue = getResources().getInteger(R.integer.saved_high_score_default_key);
int highScore = sharedPref.getInt(getString(R.string.saved_high_score_key), defaultValue);
```
## Tasks and Back Stack
A __task__ is a collection of activities that users interact with when performing a certain job. The activities are arranged in a stack—the back stack)—in the order in which each activity is opened.   

The device Home screen is the starting place for most tasks. If no task exists for the app (the app has not been used recently), then a new task is created and the "main" activity for that app opens as the root activity in the stack.  

A task is a cohesive unit that can move to the "background" when users begin a new task or go to the Home screen, via the Home button. 

To summarize the default behavior for activities and tasks:

* When Activity A starts Activity B, Activity A is stopped, but the system retains its state (such as scroll position and text entered into forms). If the user presses the Back button while in Activity B, Activity A resumes with its state restored.  
* When the user leaves a task by pressing the Home button, the current activity is stopped and its task goes into the background. The system retains the state of every activity in the task. If the user later resumes the task by selecting the launcher icon that began the task, the task comes to the foreground and resumes the activity at the top of the stack.  
* If the user presses the Back button, the current activity is popped from the stack and destroyed. The previous activity in the stack is resumed. When an activity is destroyed, the system does not retain the activity's state.  
* Activities can be instantiated multiple times, even from other tasks.  
