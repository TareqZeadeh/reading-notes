# Read: Class 36 Read: 36 - Cognito

## [Amplify and Cognito](https://docs.amplify.aws/lib/auth/getting-started/q/platform/android/)

### Configure Auth Category

1. execute the command: `amplify add auth`
1. Upon completion, amplifyconfiguration.json should be updated to reference provisioned backend auth resources.

### Install Amplify Libraries

1. Add the following dependency to your app's build.gradle: `implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'`
1. Add this line, to include the Auth plugin.

```java
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());
```

### Sign in with web UI

1. Add the following activity and queries tag to your app's `AndroidManifest.xml` file, replacing `myapp` with your redirect URI prefix if necessary:

```xml
<queries>
  <intent>
      <action android:name=
          "android.support.customtabs.action.CustomTabsService" />
  </intent>
</queries>
<application ...>
  ...
  <activity
      android:name="com.amplifyframework.auth.cognito.activities.HostedUIRedirectActivity"
      android:exported="true">
      <intent-filter>
          <action android:name="android.intent.action.VIEW" />
          <category android:name="android.intent.category.DEFAULT" />
          <category android:name="android.intent.category.BROWSABLE" />
          <data android:scheme="myapp" />
      </intent-filter>
  </activity>
  ...
</application>
```

1. Add the following result handler to whichever Activity you are calling HostedUI from:

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
    if (requestCode == AWSCognitoAuthPlugin.WEB_UI_SIGN_IN_ACTIVITY_CODE) {
        Amplify.Auth.handleWebUISignInResponse(data);
    }
}
```

### Guest access

1. The AWS Cognito Auth Plugin can be configured to automatically obtain guest credentials once the device is online so that you are able to use other categories "anonymously" without the need to sign in.

### Auth events

AWS Cognito Auth Plugin sends important events through Amplify Hub.

### User attributes

Fetch the current user's attributes

```java
Amplify.Auth.fetchUserAttributes(
    attributes -> Log.i("AuthDemo", "User attributes = " + attributes.toString()),
    error -> Log.e("AuthDemo", "Failed to fetch user attributes.", error)
);
```

### Verify user attribute

Some attributes require confirmation for the attribute update to complete. If the attribute need to be confirmed, the result of the above api will be CONFIRM_ATTRIBUTE_WITH_CODE. A confirmation code will be sent to the delivery medium mentioned in the delivery details. When the user gets the confirmation code, you can present a UI to the user to enter the code and invoke the confirm attribute api with their input

### Resend verification code

If the code has expired or the user needs to resend the confirmation code, invoke the resend api as shown below:

```java
Amplify.Auth.resendUserAttributeConfirmationCode(AuthUserAttributeKey.email(),
    result -> Log.i("AuthDemo", "Code was sent again: " + result.toString()),
    error -> Log.e("AuthDemo", "Failed to resend code.", error)
);
```

### Remember a device

1. Remembering a device is useful in conjunction with Multi-Factor Authentication (MFA). If MFA is enabled for an Amazon Cognito user pool, end users have to type in a security code received via e-mail or SMS each time they want to sign in.
1. Remembering a device allows the second factor requirement to be automatically met when the user signs in on that device, thereby reducing friction in the user experience.

### Reset password

1. In order to reset your password, use the resetPassword api - this will send a code to the user attribute configured to receive such a reset code (e.g. email or SMS):
1. To complete the password reset process, invoke the confirmResetPassword api with the code you were sent and the new password you want.

### Sign out

1. Invoke the signOut api to sign out a user from the Auth category. You can only have one user signed in at a given time.
1. Calling signOut without any options will just delete the local cache and keychain of the user. If you would like to sign out of all devices, invoke the signOut api with advanced options.

### Accessing credentials

An intentional decision with Amplify Auth was to avoid any public methods exposing credentials or manipulating them.

With Auth, you simply sign in and it handles everything else needed to keep the credentials up to date and vend them to the other categories.

However, if you need to access them in relation to working with an API outside Amplify or want access to AWS specific identifying information (e.g. IdentityId), you can access these implementation details by casting the result of fetchAuthSession