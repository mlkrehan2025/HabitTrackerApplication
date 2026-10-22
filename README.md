# Habit Tracker

Habit Tracker is a small Android app for building daily routines. You add a habit, tick it off each day, and watch your streak grow. The tagline on the splash screen says it best: small steps, big changes.

This repository holds the user interface for Task 1 of our Mobile Application Development lab. The screens and layouts are built and styled. The logic behind them (saving data, checking logins, sending reminders) comes in later tasks.

## What is in the app

The project has layouts for nine screens and one dialog:

* Splash: logo, app name, tagline and a loading bar
* Sign Up: name, email, password and confirm password fields with show and hide icons
* Login: the sign in screen (see the note under Current status)
* Home: greeting, date, quote card, today's habits with a progress bar, and an Add New Habit button
* Add Habit: habit name, category and frequency dropdowns, and a Save button
* Habit Detail: current streak, best streak, a last 7 days strip, and Edit and Delete buttons
* History: 7 Days and 30 Days tabs with a month calendar showing done and missed days
* Progress: best streak, total check ins and a list of habit streaks
* Settings: profile details, a daily reminder switch, reminder time, About and Logout
* Logout dialog: a confirmation box with Logout and Cancel

Home and Progress share a bottom navigation bar with three tabs: Today, Progress and Settings. Colours, styles and a night theme live in the values folder, so the green look stays consistent everywhere.

## Built with

* Java and XML layouts
* AndroidX AppCompat, ConstraintLayout and Material Components
* Gradle with Kotlin DSL build files
* Package name: com.example.habittrackerproject

## What you need

* Android Studio. Use the version you built the project with (you can check it under Help, About). Because the project uses a very recent Android Gradle Plugin, a current stable release of Android Studio works best, and Android Studio will offer to update if yours is too old.
* Android SDK Platform 37. The project compiles and targets API 37.
* A device or emulator running Android 6.0 (API 23) or newer. That is the minimum the app supports.
* A JDK. Android Studio ships with its own, and the project is set up to use JDK 25, so the bundled one is the easiest choice. The code itself is written for Java 11 compatibility.
* An internet connection for the first Gradle sync, since it downloads Gradle and the libraries.

The project uses Gradle 9.6.0 and Android Gradle Plugin 9.4.1. You do not need to install Gradle yourself, because the included Gradle wrapper downloads the right one.

## How to run it

1. Clone the repository:

```
git clone https://github.com/mlkrehan2025/HabitTrackerApplication.git
```

2. Open Android Studio, choose Open, and select the HabitTrackerApplication folder.
3. Wait for the Gradle sync to finish. The first sync can take a few minutes. If Android Studio asks you to install a missing SDK platform, accept it.
4. Pick where to run the app:
   * Emulator: open Device Manager, create a virtual device (a Pixel phone image works well), and start it.
   * Real phone: turn on Developer options and USB debugging in your phone settings, then connect it with a USB cable and allow the debugging prompt.
5. Press the green Run button. The app installs and opens on the Splash screen.

If you prefer the terminal, you can build a debug version from the project folder:

```
./gradlew assembleDebug
```

On Windows, use `gradlew.bat assembleDebug` instead.

## Project layout

* app/src/main/java/com/example/habittrackerproject holds the Java classes
* app/src/main/res/layout holds the screen, dialog and list item layouts
* app/src/main/res/drawable holds icons and custom backgrounds
* app/src/main/res/values holds colours, strings, styles and themes
* app/src/main/AndroidManifest.xml lists the registered screens

## Current status

This is a UI only submission, so a few things are still unfinished:

* Screens are not connected with navigation yet. Integration is planned for the next task.
* Nothing is saved. There is no database, so counters show default values such as 0 of 0 done.
* Login has no real validation, and the reminder switch does not send notifications yet.
* The Login layout currently matches the Home layout and still needs its own design.
* MainActivity is a leftover placeholder and is not part of the app flow.
* There are no separate layouts yet for About or Edit Habit.

## Team

* Hamza Khan: screen flow diagram, Splash, Sign Up and Home screens
* M. Rehan: Add Habit, Habit Detail, History, Progress and Settings screens, bottom navigation
* M. Usama: Add Habit, Habit Detail, History, Progress and Settings screens, bottom navigation

Planning, testing and the report were done together by all members.

## What comes next

* Connect the screens so every button opens the right place
* Store habits and check ins locally
* Calculate real streaks and fill the History calendar from saved data
* Add working daily reminders
