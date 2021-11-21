# Intent Filters

## [Intent Filters](https://developer.android.com/training/basics/intents/filters)

1. If your app can perform an action that might be useful from another app, your app should be prepared to respond to action requests by specifying the appropriate intent filter in your activity.

1. To allow other apps to start your activity in this way, you need to add an `<intent-filter>` element in your manifest file for the corresponding `<activity>` element.

### Add an Intent Filter

1. In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.

1. The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:
   - Action: A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.
   - Data: A description of the data associated with the intent.
   - Category: Provides an additional way to characterize the activity handling the intent, usually related to the user gesture or location from which it's started, all implicit intents are defined with CATEGORY_DEFAULT by default.
1. Each incoming intent specifies only one action and one data type, but it's OK to declare multiple instances of the `<action>`, `<category>`, and `<data>` elements in each `<intent-filter>`.

### Handle the Intent in Your Activity

1. As your activity starts, call getIntent() to retrieve the Intent that started the activity. You can do so at any time during the lifecycle of the activity, but you should generally do so during early callbacks such as onCreate() or onStart().
1. When your operation is done and the user should return to the original activity, call finish() to close (and destroy) your activity.
1. You must always specify a result code with the result. Generally, it's either RESULT_OK or RESULT_CANCELED.