# Intents, Activities, and SharedPreferences

## [Android Tasks and the Back Stack](https://developer.android.com/guide/components/activities/tasks-and-back-stack)

1. A task is a collection of activities that users interact with when performing a certain job. The activities are arranged in a stack—the back stack—in the order in which each activity is opened.
   ![taskStack](https://developer.android.com/images/fundamentals/diagram_backstack.png)
1. Multiple tasks can be held in the background at once. However, if the user is running many background tasks at the same time, the system might begin destroying background activities in order to recover memory, causing the activity states to be lost.

1. When Activity A starts Activity B, Activity A is stopped, but the system retains its state (such as scroll position and text entered into forms). If the user presses the Back button while in Activity B, Activity A resumes with its state restored.
1. When the user leaves a task by pressing the Home button, the current activity is stopped and its task goes into the background. The system retains the state of every activity in the task. If the user later resumes the task by selecting the launcher icon that began the task, the task comes to the foreground and resumes the activity at the top of the stack.
1. If the user presses the Back button, the current activity is popped from the stack and destroyed. The previous activity in the stack is resumed. When an activity is destroyed, the system does not retain the activity's state.
1. Activities can be instantiated multiple times, even from other tasks.

### Managing Tasks

1. the principal `<activity>` attributes you can use are:

   - taskAffinity
   - launchMode
   - allowTaskReparenting
   - clearTaskOnLaunch
   - alwaysRetainTaskState
   - finishOnTaskLaunch

1. the principal intent flags you can use are:

   - FLAG_ACTIVITY_NEW_TASK
   - FLAG_ACTIVITY_CLEAR_TOP
   - FLAG_ACTIVITY_SINGLE_TOP

1. Most apps should not interrupt the default behavior for activities and tasks. If you determine that it's necessary for your activity to modify the default behaviors, use caution and be sure to test the usability of the activity during launch and when navigating back to it from other activities and tasks with the Back button. Be sure to test for navigation behaviors that might conflict with the user's expected behavior.

#### Defining launch modes

1. You can define different launch modes in two ways:

   - Using the manifest file

     - When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

   - Using Intent flags
     - When you call startActivity(), you can include a flag in the Intent that declares how (or whether) the new activity should associate with the current task.

### Handling affinities

1. The affinity indicates which task an activity prefers to belong to. By default, all the activities from the same app have an affinity for each other.
1. You can modify the affinity for any given activity with the taskAffinity attribute of the `<activity>` element.
1. The affinity comes into play in two circumstances:
   - When the intent that launches an activity contains the FLAG_ACTIVITY_NEW_TASK flag.
     - the system looks for a different task to house the new activity. Often, it's a new task. However, it doesn't have to be. If there's already an existing task with the same affinity as the new activity, the activity is launched into that task. If not, it begins a new task.
   - When an activity has its allowTaskReparenting attribute set to "true".
1. If an APK file contains more than one "app" from the user's point of view, you probably want to use the taskAffinity attribute to assign different affinities to the activities associated with each "app".

### Clearing the back stack

1. If the user leaves a task for a long time, the system clears the task of all activities except the root activity.
1. There are some activity attributes that you can use to modify this behavior:

   - alwaysRetainTaskState: If this attribute is set to "true" in the root activity of a task, the default behavior just described does not happen. The task retains all activities in its stack even after a long period.
   - clearTaskOnLaunch: If this attribute is set to "true" in the root activity of a task, the task is cleared down to the root activity whenever the user leaves the task and returns to it. In other words, it's the opposite of alwaysRetainTaskState
     - This attribute is ignored if FLAG_ACTIVITY_RESET_TASK_IF_NEEDED isn't set.
   - finishOnTaskLaunch: This attribute is like clearTaskOnLaunch, but it operates on a single activity, not an entire task. It can also cause any activity to finish, except for the root activity. When it's set to "true", the activity remains part of the task only for the current session. If the user leaves and then returns to the task, it is no longer present.
     - This attribute is ignored if FLAG_ACTIVITY_RESET_TASK_IF_NEEDED isn't set.

### Starting a task

1. You can set up an activity as the entry point for a task by giving it an intent filter with `"android.intent.action.MAIN"` as the specified action and `"android.intent.category.LAUNCHER"` as the specified category.
1. An intent filter of this kind causes an icon and label for the activity to be displayed in the app launcher, giving users a way to launch the activity and to return to the task that it creates any time after it has been launched.
1. This second ability is important: Users must be able to leave a task and then come back to it later using this activity launcher. For this reason, the two launch modes that mark activities as always initiating a task, "singleTask" and "singleInstance", should be used only when the activity has an ACTION_MAIN and a CATEGORY_LAUNCHER filter.

## [Android SharedPreferences](https://developer.android.com/training/data-storage/shared-preferences)

1.  A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them. Each SharedPreferences file is managed by the framework and can be private or shared.

### Get a handle to shared preferences

1. You can create a new shared preference file or access an existing one by calling one of these methods:
   - `getSharedPreferences()` — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.
   - `getPreferences()` — Use this from an Activity if you need to use only one shared preference file for the activity.
1. When naming your shared preference files, you should use a name that's uniquely identifiable to your app.
1. If you're using the SharedPreferences API to save app settings, you should instead use getDefaultSharedPreferences() to get the default shared preference file for your entire app.

### Write to shared preferences

1. To write to a shared preferences file, create a SharedPreferences.Editor by calling edit() on your SharedPreferences.
1. You can edit shared preferences in a more secure way by calling the edit() method on an EncryptedSharedPreferences object instead of on a SharedPreferences object.
1. Pass the keys and values you want to write with methods such as putInt() and putString(). Then call apply() or commit() to save the changes.

### Read from shared preferences

1. To retrieve values from a shared preferences file, call methods such as getInt() and getString(), providing the key for the value you want, and optionally a default value to return if the key isn't present.