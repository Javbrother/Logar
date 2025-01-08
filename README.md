LOGAR
Overview
This Android application demonstrates how to integrate Google Sign-In with Firebase Authentication. It allows users to sign in using their Google account and displays a simple greeting message upon successful authentication.

Features
Google Sign-In: Utilizes the GoogleSignInClient to prompt users to log in with their Google account.
Firebase Authentication: Exchanges Google Sign-In credentials for a Firebase Auth token, then obtains the user’s info from Firebase.
User Greeting: Displays the logged-in user’s display name on the screen.
Requirements
Android Studio (latest stable version recommended).
Firebase project configured for Android:
A valid google-services.json in the app/ folder.
Enable Google Sign-In in your Firebase Console under Authentication → Sign-in methods.
Google APIs:
You need to have created a Web client OAuth 2.0 client ID in the Google Cloud Console.
Make sure to match the SHA-1 fingerprint of your app and the package name.
Internet access in your AndroidManifest.xml if needed for any network operations.
Getting Started
Clone or Download the Repository

Open the project in Android Studio.
Configure Firebase

Go to the Firebase Console.
Create or select an existing Firebase project.
Add an Android app to the project, providing your app’s package name and SHA-1 fingerprint.
Download the google-services.json file from the Firebase Console and place it in the app/ directory of your project.
Enable Google Sign-In

In the Firebase Console, navigate to Authentication → Sign-in method.
Enable Google as a sign-in provider.
Update default_web_client_id

In your Firebase project settings, ensure the Web client ID is added to your Google Sign-In configuration.
Copy the Web client ID from the Firebase project and add it to your strings.xml (referenced as @string/default_web_client_id).
Sync and Build

In Android Studio, click Sync Project to pull in all Gradle dependencies.
Usage
Launch the App

Run the project on an emulator or a physical device.
Sign In

Tap the Sign In button (linked to signIn(View view) in MainActivity).
A Google Sign-In prompt will appear.
Authentication

After signing in with your Google account, Firebase Authentication will process the credentials.
On success, the app will display your Display Name on the screen.
Troubleshooting

If sign-in fails, check the Logcat for ApiException or FirebaseAuth errors.
Common issues involve incorrect SHA-1 fingerprints or mismatched client IDs.
File Breakdown
MainActivity.java

Handles Google Sign-In (signIn()) and listens for results in onActivityResult().
On successful sign-in, obtains an ID token and exchanges it for Firebase credentials (firebaseAuthWithGoogle()).
Updates the UI with a greeting that includes the user’s display name.
activity_main.xml (Layout)

Contains a Sign In button and a TextView (user_info) to display the greeting.
strings.xml

Houses the default_web_client_id reference to your Firebase web client ID.
AndroidManifest.xml

General Android app configuration.
Make sure you have the INTERNET permission if needed.
Libraries Used
Firebase Authentication
Google Sign-In
AndroidX libraries (AppCompat, etc.).
Contributing
If you wish to enhance this project, feel free to fork it and submit a pull request with your improvements or open issues for any bugs or feature requests.

License
This project is provided as-is for demonstration purposes. Refer to any included license file or consult with the project owner for additional license details.
