# Read: Class 26 Read: 26 - Android Fundamentals

## [Android fundamentals](https://developer.android.com/guide/components/fundamentals)

1. Android package, which is an archive file with an .apk suffix, contains the contents of an Android app that are required at runtime and it is the file that Android-powered devices use to install the app.
1. Android App Bundle, which is an archive file with an .aab suffix, contains the contents of an Android app project including some additional metadata that is not required at runtime.
1. Each Android app lives in its own security sandbox, protected by the following Android security features:
   - The Android operating system is a multi-user Linux system in which each app is a different user.
   - By default, the system assigns each app a unique Linux user ID
   - Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
   - By default, every app runs in its own Linux process.
1. The Android system implements the principle of least privilege. That is, each app, by default, has access only to the components that it requires to do its work and no more.

### App components

1. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.
1. There are four different types of app components:

   - Activities
   - Services
   - Broadcast receivers
   - Content providers

1. Activities
   - An activity is the entry point for interacting with the user. It represents a single screen with a user interface.
   - Although the activities work together to form a cohesive user experience in the email app, each one is independent of the others. As such, a different app can start any one of these activities if the email app allows it.
   - An activity facilitates the following key interactions between system and app:
     - Keeping track of what the user currently cares about (what is on screen) to ensure that the system keeps running the process that is hosting the activity.
     - Knowing that previously used processes contain things the user may return to (stopped activities), and thus more highly prioritize keeping those processes around.
     - Helping the app handle having its process killed so the user can return to activities with their previous state restored.
     - Providing a way for apps to implement user flows between each other, and for the system to coordinate these flows.
1. Services
   - A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons.
   - It is a component that runs in the background to perform long-running operations or to perform work for remote processes.
   - if process A is bound to a service in process B, it knows that it needs to keep process B (and its service) running for A. Further, if process A is something the user cares about, then it also knows to treat process B as something the user also cares about. Because of their flexibility (for better or worse), services have turned out to be a really useful building block for all kinds of higher-level system concepts.
1. Broadcast receivers
   - A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements.
1. Content providers
   - A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access.
   - Content providers are also useful for reading and writing data that is private to your app and not shared.
1. A unique aspect of the Android system design is that any app can start another app’s component. Therefore, unlike apps on most other systems, Android apps don't have a single entry point (there's no main() function).
1. To activate a component in another app, deliver a message to the system that specifies your intent to start a particular component. The system then activates the component for you.

### Activating components

1. Three of the four component types—activities, services, and broadcast receivers—are activated by an asynchronous message called an intent
1. Intents bind individual components to each other at runtime.
1. An intent is created with an `Intent` object, which defines a message to activate either a specific component (explicit intent) or a specific type of component (implicit intent).
1. you can issue an intent to let the user pick a personal contact and have it returned to you. The return intent includes a URI pointing to the chosen contact.
1. For broadcast receivers, the intent simply defines the announcement being broadcast.
1. content providers are not activated by intents. Rather, they are activated when targeted by a request from a `ContentResolver`.
1. There are separate methods for activating each type of component:

   - You can start an activity or give it something new to do by passing an Intent to startActivity() or startActivityForResult() (when you want the activity to return a result).
   - With Android 5.0 (API level 21) and later, you can use the JobScheduler class to schedule actions. For earlier Android versions, you can start a service (or give new instructions to an ongoing service) by passing an Intent to startService(). You can bind to the service by passing an Intent to bindService().
   - You can initiate a broadcast by passing an Intent to methods such as sendBroadcast(), sendOrderedBroadcast(), or sendStickyBroadcast().
   - You can perform a query to a content provider by calling query() on a ContentResolver.

### The manifest file

1. Before the Android system can start an app component, the system must know that the component exists by reading the app's manifest file, `AndroidManifest.xml`.
1. The manifest does a number of things in addition to declaring the app's components, such as the following:
   - Identifies any user permissions the app requires, such as Internet access or read-access to the user's contacts.
   - Declares the minimum API Level required by the app, based on which APIs the app uses.
   - Declares hardware and software features used or required by the app, such as a camera, bluetooth services, or a multitouch screen.
   - Declares API libraries the app needs to be linked against (other than the Android framework APIs), such as the Google Maps library.

### Declaring components

1. In the `<application>` element, the android:icon attribute points to resources for an icon that identifies the app.
1. In the `<activity>` element, the android:name attribute specifies the fully qualified class name of the `Activity` subclass and the android:label attribute specifies a string to use as the user-visible label for the activity.
1. You must declare all app components using the following elements:

   - `<activity>` elements for activities.
   - `<service>`elements for services.
   - `<receiver>` elements for broadcast receivers.
   - `<provider>` elements for content providers.

1. broadcast receivers can be either declared in the manifest or created dynamically in code as `BroadcastReceiver` objects and registered with the system by calling `registerReceiver()`.

### Declaring component capabilities

1. When you declare an activity in your app's manifest, you can optionally include intent filters that declare the capabilities of the activity so it can respond to intents from other apps. You can declare an intent filter for your component by adding an `<intent-filter>` element as a child of the component's declaration element.

### Declaring app requirements

1. To prevent your app from being installed on devices that lack features needed by your app, it's important that you clearly define a profile for the types of devices your app supports by declaring device and software requirements in your manifest file.

### App resources

1. One of the most important aspects of providing resources separate from your source code is the ability to provide alternative resources for different device configurations.