# Notifications

## [SNS: Getting Started](https://aws.amazon.com/sns/getting-started/)

- Amazon Simple Notification Service (Amazon SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.
- Amazon SNS enables you to modernize your applications and decouple them into smaller, independent components that are easier to develop, deploy, and maintain.
- Amazon SNS enables you to send messages or notifications directly to users with SMS text messages to over 200 countries, mobile push on Apple, Android, and other platforms or email (SMTP).
- Amazon SNS uses a number of strategies that work together to provide message durability. To start, published messages are stored across multiple, geographically-separated servers and data centers. If a subscribed endpoint isn't available, Amazon SNS executes a message delivery retry policy.
- ![How it works](https://d1.awsstatic.com/product-marketing/SNS/Product-Page-Diagram_Amazon-SNS_3-Mobile-Push-How-it-works%401.5x.fdb05d0c3e659250336fbead899573e5fb698321.png)
  
## [SNS with Amplify (and Firebase)](https://docs.amplify.aws/sdk/push-notifications/getting-started/q/platform/android/)

- Set Up Your App

  - Use the CLI to add storage to your cloud-enabled backend and app. `amplify add notifications`
  - Set up your backend to support receiving push notifications: 
    - Choose Firebase Cloud Messaging (FCM).
    - Provide your ApiKey. The FCM console refers to this value as ServerKey.
  - Add the following dependencies and plugin to your app/build.gradle:

    ```
    dependencies {
        // Overrides an auth dependency to ensure correct behavior
        implementation 'com.google.android.gms:play-services-auth:19.2.0'
        // Import the BoM for the Firebase platform
        implementation platform('com.google.firebase:firebase-bom:28.2.1')
        implementation 'com.google.firebase:firebase-messaging'
        implementation 'com.amazonaws:aws-android-sdk-pinpoint:2.25.+'
        implementation ('com.amazonaws:aws-android-sdk-mobile-client:2.26.+@aar') { transitive = true }
    }
    apply plugin: 'com.google.gms.google-services'
    ```

  - AndroidManifest.xml must contain the definition of the following service for PushListenerService in the application tag:

    ```
    <service
        android:name=".PushListenerService">
        <intent-filter>
            <action android:name="com.google.firebase.MESSAGING_EVENT"/>
        </intent-filter>
    </service>
    ```

  - Create an Amazon Pinpoint client in the location of your push notification code.