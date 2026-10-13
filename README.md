# Pedago Math: Login System

A Flutter login screen for the Pedago Math app. It signs registered users in with their email address and password using Firebase Authentication. This project is a work in progress.

Interactive demo page:https://23008024.github.io/pedago-math-login-Test/

## About the project

Pedago Math uses a login screen built with Flutter and Dart. A registered user types in an email address and a password. The app first checks that what was typed looks correct, then Firebase Authentication checks that the email and password belong to a real account. If something goes wrong, the screen shows a message.

## What the login screen includes

The screen is written in the file lib/screens/login_screen.dart and uses Flutter's Form and TextFormField widgets. It has an email field, a password field, a button to show or hide the password, a Remember Me checkbox, a Forgot Password option, a Login button, and a link to the registration screen.

## Checking the input

Before the app contacts Firebase, it checks what the user typed. The email must not be empty and must look like a real email address. The password must not be empty and must have at least eight characters. If a check fails, the app shows a message and stops there. These checks only look at the format. Firebase decides whether the account is real.

## Signing in with Firebase

The app signs users in with Firebase Authentication's signInWithEmailAndPassword method. If sign-in works, the app shows a login success message. If it fails, the app shows an error message. The screen handles four kinds of problems: wrong credentials, an invalid email address, a disabled account, and too many login attempts. After each waiting step, the app also checks that the screen is still open before changing it.

## Remember Me

When Remember Me is turned on, the app saves the user's choice and their email address on the device, using the shared_preferences package. The next time the login screen opens, the email is filled in again. When Remember Me is turned off, the saved email is removed. The password is never saved.

## Testing

Automated tests run with this command:

    flutter test

The result is: All tests passed!

Two automated tests pass. One checks that the main elements of the login screen are shown. The other checks that an empty email field is rejected.

I also tested by hand with Firebase: signing in with valid credentials, signing in with a wrong password, and signing in with an email that has no account. All three behaved as expected.

## Current status

Done so far: the login screen, input checks, Firebase sign-in, error messages, Remember Me, two automated tests, and manual testing.

Still to do: move the user to the home screen after a successful login, connect Forgot Password to Firebase password reset, and add more automated tests for signing in.

## Technologies

Flutter builds the screen. Dart is the programming language. Firebase Authentication handles sign-in. SharedPreferences stores the Remember Me choice and the saved email. Flutter Test runs the automated tests.
