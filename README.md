# flutter_notification

A new Flutter application.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
# flutter_notification

# How to Setup

- dependencies:
   firebase_messaging: ^5.1.5
   firebase_analytics: ^5.0.2

Android Integration #
To integrate your plugin into the Android part of your app, follow these steps:

# Using the Firebase Console add an Android app to your project: Follow the assistant, download the generated google-services.json file and place it inside android/app.

# Add the classpath to the [project]/android/build.gradle file.

buildscript {
 // Example existing kotlin_version
    ext.kotlin_version = '1.3.0'
    }
    
dependencies {
  // Example existing classpath
  classpath 'com.android.tools.build:gradle:3.3.0'
  // Add the google services classpath
  classpath 'com.google.gms:google-services:4.3.2'
}

# Add the apply plugin to the [project]/android/app/build.gradle file.

    dependencies {
        implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk7:$kotlin_version"
        testImplementation 'junit:junit:4.12'
        androidTestImplementation 'androidx.test:runner:1.1.1'
        androidTestImplementation 'androidx.test.espresso:espresso-core:3.1.1'
    }

   // ADD THIS AT THE BOTTOM
    apply plugin: 'com.google.gms.google-services'
    
    
   Note: If this section is not completed you will get an error like this:

   java.lang.IllegalStateException:
   Default FirebaseApp is not initialized in this process [package name].
   Make sure to call FirebaseApp.initializeApp(Context) first.
   Note: When you are debugging on Android, use a device or AVD with Google Play services. Otherwise you will not be able to     
   authenticate.

# (optional, but recommended) If want to be notified in your app (via onResume and onLaunch, see below) when the user clicks on    a notification in the system tray include the following intent-filter within the <activity> tag of your         
    android/app/src/main/AndroidManifest.xml:
  
  <intent-filter>
      <action android:name="FLUTTER_NOTIFICATION_CLICK" />
      <category android:name="android.intent.category.DEFAULT" />
  </intent-filter>
  
  
