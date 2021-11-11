# Read: Class 31 Read: 31 - Espresso

## [Espresso](https://developer.android.com/training/testing/espresso)

1. Use Espresso to write concise, beautiful, and reliable Android UI tests.

### Synchronization capabilities

1. Each time your test invokes onView(), Espresso waits to perform the corresponding UI action or assertion until the following synchronization conditions are met:

   - The message queue is empty.
   - There are no instances of AsyncTask currently executing a task.
   - All developer-defined idling resources are idle.

1. By performing these checks, Espresso substantially increases the likelihood that only one UI action or assertion can occur at any given time.

### Packages

1. `espresso-core` - Contains core and basic View matchers, actions, and assertions
1. `espresso-web` - Contains resources for WebView support.
1. `espresso-idling-resource` - Espresso's mechanism for synchronization with background jobs.
1. `espresso-contrib` - External contributions that contain `DatePicker`, `RecyclerView` and `Drawer` actions, accessibility checks, and `CountingIdlingResource`.
1. `espresso-intents` - Extension to validate and stub intents for hermetic testing.
1. `espresso-remote` - Location of Espresso's multi-process functionality.

## [Ridiculous superpower: the Espresso Test Recorder](https://developer.android.com/studio/test/espresso-test-recorder)

1. The Espresso Test Recorder tool lets you create UI tests for your app without writing any test code.
1. Espresso Test Recorder writes tests based on the Espresso Testing framework, an API in AndroidX Test.

### Turn off animations on your test device

1. Before using Espresso Test Recorder, make sure you turn off animations on your test device to prevent unexpected results.

### Record an Espresso test

1. Espresso tests consist of two primary components: UI interactions and assertions on View elements.
   - UI interactions include tap and type actions that a person may use to interact with your app
   - Assertions verify the existence or contents of visual elements on the screen.
1. To start recording a test with Espresso Test Recorder, proceed as follows:
   - Click Run > Record Espresso Test.
   - In the Select Deployment Target window, choose the device on which you want to record the test. If necessary, create a new Android Virtual Device. Click OK.
   - Espresso Test Recorder triggers a build of your project, and the app must install and launch before Espresso Test Recorder allows you to interact with it.

### Add assertions to verify UI elements

1. Assertions verify the existence or contents of a View element through three main types:
   - text is: Checks the text content of the selected View element
   - exists: Checks that the View element is present in the current View hierarchy visible on the screen
   - does not exist: Checks that the View element is not present in the current View hierarchy

### Save a recording

1. Once you finish interacting with your app and adding assertions, use the following steps to save your recording and generate the Espresso test:
   - Click Complete Recording. The Pick a test class name for your test window appears.
   - Espresso Test Recorder gives your test a unique name within its package based on the name of the launched activity.
   - The file automatically opens after Espresso Test Recorder generates it, and Android Studio shows the test class as selected in the Project window of the IDE.

### Run an Espresso test locally

1. To run an Espresso test, use the Project window on the left side of the Android Studio IDE