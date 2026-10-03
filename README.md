💪 FORTIS



Offline-First Fitness, Workout & Nutrition Tracker



FORTIS is a mobile fitness companion focusing on fast workout

logging, offline-first data, progressive overload, analytics,

Indian-food-first nutrition, and sustainable habit tracking.



Built with React Native + Expo + Firebase, FORTIS is designed to

be useful even when you're at the gym and the connectivity is



unstable or unavailable.



🚀 Features



🏋️ Workout Logging



Log sets with weight, reps, optional RPE, and set type.



Supported set types:



Warm-up



Working



Drop



Failure



Automatically prefill values from the previous session.



Start workouts from templates:



Push / Pull / Legs



Upper / Lower



Full Body



Repeat the previous workout in one tap.



Rest timer continues running even when the screen is locked.



In-progress workouts survive crashes and force-close without

losing logged sets.



Exercise library with 150+ exercises.



Search exercises by:



Muscle group



Equipment



Create custom exercises.



Gym-friendly interface with:



Large controls



One-handed interaction



Dark mode



📡 Offline-First Sync



FORTIS is designed for unreliable gym and mobile networks.



Core functionality works without an internet connection.



Workout and nutrition data are saved locally first.



Data synchronizes automatically in the background when connectivity

returns.



Displays a "N changes waiting to sync" status.



Supports multiple devices.



Prevents duplicate records during synchronization.



Handles conflicts when the same record is edited on multiple

devices.



Core idea:



User Action

↓

Save Locally

↓

Continue Using App

↓

Network Available

↓

Background Sync

↓

Firebase



📈 Progression & Analytics



FORTIS helps users to understand their progress, not just store

workout history.



Suggests the next session's:



Weight



Reps



Explains progression suggestions.



Example:



You hit 3 × 12 at 60 kg, so try 62.5 kg.



Estimated 1RM.



Automatic personal-record detection.



Training-volume charts.



Weekly sets by muscle group.



Progress dashboard containing:



Today's workout



Calorie ring



Macro rings



Weight trend



Streak



🍛 Indian-Food-First Nutrition



Nutrition tracking is designed around foods and serving sizes commonly

used in India.



Food Search



Typo-tolerant search.



Synonym support.



Example: chapati, phulka, roti can resolve to the same food item.



Indian Portion Units



Support for practical serving units such as:



Katori



Roti



Glass



Piece



Quick Logging



Custom foods.



Quick add.



Copy yesterday's meals.



Offline food search using a downloadable pack of common foods.



Daily Tracking



Track:



Calories



Protein



Carbohydrates



Fat



Fibre



Against personalized daily targets.



🎯 Targets & Habits



FORTIS uses a short onboarding flow to establish personalized targets.



60-second onboarding assessment.



Calculates calorie and macro targets.



Safety rules for calorie targets.



Calorie floors.



No deficit targets for users under 18.



Option to hide calorie numbers.



Weekly streaks.



Rest-day credits so planned recovery days do not break streaks.



Gentle, non-aggressive reminders.



🧱 Tech Stack



Layer Technology



Mobile App React Native

App Framework Expo

Authentication Firebase Authentication

Database Cloud Firestore

File Storage Firebase Storage

Backend Logic Firebase Cloud Functions

Notifications Firebase Cloud Messaging

Analytics Firebase Analytics

Crash Monitoring Firebase Crashlytics

Build & Distribution Expo EAS



🏗️ High-Level Architecture

┌───────────────────┐



│ USERS │

│ Android / iOS │

└─────────┬─────────┘

│

▼

┌──────────────────────────┐

│ React Native + Expo │

│ Mobile App │

│ │

│ Workout │ Nutrition │

│ Analytics │ Progression │

│ Profile │ Habits │

└────────────┬─────────────┘

│

HTTPS / Firebase SDK

│

▼

┌──────────────────┐

│ API / Cloud │

│ Functions │

│ │

│ Business Logic │

│ Validation │

│ Progression │

│ Nutrition │

│ Scheduled Jobs │

└────────┬─────────┘

│

┌──────────────────┼──────────────────┐

▼ ▼ ▼

┌─────────────┐ ┌─────────────┐ ┌─────────────┐

│ Firestore │ │ Storage │ │ FCM │

│ │ │ │ │ │

│ Users │ │ Images │ │ Reminders │

│ Workouts │ │ Videos │ │ Streaks │

│ Sets │ │ Media │ │ Updates │

│ Meals │ │ │ │ │

└─────────────┘ └─────────────┘ └─────────────┘

┌─────────────────────────────┐



│ Analytics + Crashlytics │

│ Usage / Errors / Stability │

└─────────────────────────────┘



📱 Core Product Flow



Install

↓

Onboarding Assessment

↓

Set Goals & Targets

↓

Dashboard

├── Workout

│ ├── Choose Template

│ ├── Log Sets

│ ├── Rest Timer

│ └── Save Progress

│

├── Nutrition

│ ├── Search Food

│ ├── Select Portion

│ └── Track Macros

│

├── Analytics

│ ├── PRs

│ ├── Volume

│ ├── Weight Trend

│ └── Muscle Group Progress

│

└── Habits

├── Streaks

├── Rest Days

└── Reminders



🔄 Offline-First Philosophy



FORTIS follows a local-first user experience.



User should not have to wait for a server response before continuing

a workout.

┌───────────────┐



│ User Logs │

│ Set │

└───────┬───────┘

↓

┌───────────────┐

│ Local Cache │

│ / DB │

└───────┬───────┘

↓

UI Updates

│

┌──────────┴──────────┐

│ │

Offline Online

│ │

↓ ↓

Keep Working Background Sync

│

↓

Firebase



This approach is particularly important for gym environments where

connectivity may be inconsistent.



📂 Suggested Project Structure



fortis/

│

├── app/

│ ├── screens/

│ ├── navigation/

│ └── components/

│

├── features/

│ ├── workout/

│ ├── nutrition/

│ ├── progression/

│ ├── analytics/

│ ├── habits/

│ └── profile/

│

├── services/

│ ├── firebase/

│ ├── auth/

│ ├── firestore/

│ ├── storage/

│ └── notifications/

│

├── hooks/

├── utils/

├── constants/

├── assets/

│

├── functions/

│ ├── progression/

│ ├── nutrition/

│ ├── notifications/

│ └── analytics/

│

├── app.json

├── eas.json

└── package.json



🛠️ Getting Started



1. Clone the repository



git clone

cd fortis



2. Install dependencies



npm install



3. Start Expo



npx expo start



You can then run the application using:



Android emulator



iOS simulator



Expo Go



Development build



🔐 Firebase Configuration



FORTIS uses Firebase for its backend services.



Configure:



Firebase Authentication



Cloud Firestore



Firebase Storage



Firebase Cloud Functions



Firebase Cloud Messaging



Firebase Analytics



Firebase Crashlytics



Keep Firebase configuration and secrets outside source-controlled

sensitive files where appropriate.



📦 Build & Deployment



FORTIS uses Expo EAS for application builds and distribution.



Developer

↓

Expo CLI

↓

EAS Build

↓

Android / iOS

↓

App Distribution



🎯 Launch Scope --- P0



Module Launch Status



Workout Logging P0

Offline-First Sync P0

Progression & Analytics P0

Indian-Food-First Nutrition P0

Targets & Habits P0



🧭 Product Vision



FORTIS aims to make fitness tracking fast enough for the gym,

practical enough for everyday nutrition, and reliable enough to work

without a network.



The core principle is simple:



Log less. Understand more. Progress consistently.



📌 Project Status



🚧 FORTIS is under active development.



The launch version focuses on the P0 feature set described above, with

additional capabilities planned for future releases.



👨‍💻 Development



Built with:



React Native · Expo · Firebase



📄 License



Add the project's license information here before publishing the

repository.💪 FORTIS

Offline-First Fitness, Workout & Nutrition Tracker

FORTIS is a mobile fitness companion focused on fast workout

logging, offline-first data, progressive overload, analytics,

Indian-food-first nutrition, and sustainable habit tracking.

Built with React Native + Expo + Firebase, FORTIS is designed to

be useful even when you're at the gym and the connectivity is

unstable or unavailable.

🚀 Features

🏋️ Workout Logging

Log sets with weight, reps, optional RPE, and set type.

Supported set types:

Warm-up

Working

Drop

Failure

Automatically prefill values from the previous session.

Start workouts from templates:

Push / Pull / Legs

Upper / Lower

Full Body

Repeat the previous workout in one tap.

Rest timer continues running even when the screen is locked.

In-progress workouts survive crashes and force-close without

losing logged sets.

Exercise library with 150+ exercises.

Search exercises by:

Muscle group

Equipment

Create custom exercises.

Gym-friendly interface with:

Large controls

One-handed interaction

Dark mode

📡 Offline-First Sync

FORTIS is designed for unreliable gym and mobile networks.

Core functionality works without an internet connection.

Workout and nutrition data are saved locally first.

Data synchronizes automatically in the background when connectivity

returns.

Displays a "N changes waiting to sync" status.

Supports multiple devices.

Prevents duplicate records during synchronization.

Handles conflicts when the same record is edited on multiple

devices.

Core idea:

User Action

↓

Save Locally

↓

Continue Using App

↓

Network Available

↓

Background Sync

↓

Firebase

📈 Progression & Analytics

FORTIS helps users to understand their progress, not just store

workout history.

Suggests the next session's:

Weight

Reps

Explains progression suggestions.

Example:

You hit 3 × 12 at 60 kg, so try 62.5 kg.

Estimated 1RM.

Automatic personal-record detection.

Training-volume charts.

Weekly sets by muscle group.

Progress dashboard containing:

Today's workout

Calorie ring

Macro rings

Weight trend

Streak

🍛 Indian-Food-First Nutrition

Nutrition tracking is designed around foods and serving sizes commonly

used in India.

Food Search

Typo-tolerant search.

Synonym support.

Example: chapati, phulka, roti can resolve to the same food item.

Indian Portion Units

Support for practical serving units such as:

Katori

Roti

Glass

Piece

Quick Logging

Custom foods.

Quick add.

Copy yesterday's meals.

Offline food search using a downloadable pack of common foods.

Daily Tracking

Track:

Calories

Protein

Carbohydrates

Fat

Fibre

Against personalized daily targets.

🎯 Targets & Habits

FORTIS uses a short onboarding flow to establish personalized targets.

60-second onboarding assessment.

Calculates calorie and macro targets.

Safety rules for calorie targets.

Calorie floors.

No deficit targets for users under 18.

Option to hide calorie numbers.

Weekly streaks.

Rest-day credits so planned recovery days do not break streaks.

Gentle, non-aggressive reminders.

🧱 Tech Stack

Layer Technology

Mobile App React Native

App Framework Expo

Authentication Firebase Authentication

Database Cloud Firestore

File Storage Firebase Storage

Backend Logic Firebase Cloud Functions

Notifications Firebase Cloud Messaging

Analytics Firebase Analytics

Crash Monitoring Firebase Crashlytics

Build & Distribution Expo EAS

🏗️ High-Level Architecture

┌───────────────────┐

│ USERS │

│ Android / iOS │

└─────────┬─────────┘

│

▼

┌──────────────────────────┐

│ React Native + Expo │

│ Mobile App │

│ │

│ Workout │ Nutrition │

│ Analytics │ Progression │

│ Profile │ Habits │

└────────────┬─────────────┘

│

HTTPS / Firebase SDK

│

▼

┌──────────────────┐

│ API / Cloud │

│ Functions │

│ │

│ Business Logic │

│ Validation │

│ Progression │

│ Nutrition │

│ Scheduled Jobs │

└────────┬─────────┘

│

┌──────────────────┼──────────────────┐

▼ ▼ ▼

┌─────────────┐ ┌─────────────┐ ┌─────────────┐

│ Firestore │ │ Storage │ │ FCM │

│ │ │ │ │ │

│ Users │ │ Images │ │ Reminders │

│ Workouts │ │ Videos │ │ Streaks │

│ Sets │ │ Media │ │ Updates │

│ Meals │ │ │ │ │

└─────────────┘ └─────────────┘ └─────────────┘

┌─────────────────────────────┐

│ Analytics + Crashlytics │

│ Usage / Errors / Stability │

└─────────────────────────────┘

📱 Core Product Flow

Install

↓

Onboarding Assessment

↓

Set Goals & Targets

↓

Dashboard

├── Workout

│ ├── Choose Template

│ ├── Log Sets

│ ├── Rest Timer

│ └── Save Progress

│

├── Nutrition

│ ├── Search Food

│ ├── Select Portion

│ └── Track Macros

│

├── Analytics

│ ├── PRs

│ ├── Volume

│ ├── Weight Trend

│ └── Muscle Group Progress

│

└── Habits

├── Streaks

├── Rest Days

└── Reminders

🔄 Offline-First Philosophy

FORTIS follows a local-first user experience.

User should not have to wait for a server response before continuing

a workout.

┌───────────────┐

│ User Logs │

│ Set │

└───────┬───────┘

↓

┌───────────────┐

│ Local Cache │

│ / DB │

└───────┬───────┘

↓

UI Updates

│

┌──────────┴──────────┐

│ │

Offline Online

│ │

↓ ↓

Keep Working Background Sync

│

↓

Firebase

This approach is particularly important for gym environments where

connectivity may be inconsistent.

📂 Suggested Project Structure

fortis/

│

├── app/

│ ├── screens/

│ ├── navigation/

│ └── components/

│

├── features/

│ ├── workout/

│ ├── nutrition/

│ ├── progression/

│ ├── analytics/

│ ├── habits/

│ └── profile/

│

├── services/

│ ├── firebase/

│ ├── auth/

│ ├── firestore/

│ ├── storage/

│ └── notifications/

│

├── hooks/

├── utils/

├── constants/

├── assets/

│

├── functions/

│ ├── progression/

│ ├── nutrition/

│ ├── notifications/

│ └── analytics/

│

├── app.json

├── eas.json

└── package.json

🛠️ Getting Started

1. Clone the repository

git clone

cd fortis

2. Install dependencies

npm install

3. Start Expo

npx expo start

You can then run the application using:

Android emulator

iOS simulator

Expo Go

Development build

🔐 Firebase Configuration

FORTIS uses Firebase for its backend services.

Configure:

Firebase Authentication

Cloud Firestore

Firebase Storage

Firebase Cloud Functions

Firebase Cloud Messaging

Firebase Analytics

Firebase Crashlytics

Keep Firebase configuration and secrets outside source-controlled

sensitive files where appropriate.

📦 Build & Deployment

FORTIS uses Expo EAS for application builds and distribution.

Developer

↓

Expo CLI

↓

EAS Build

↓

Android / iOS

↓

App Distribution

🎯 Launch Scope --- P0

Module Launch Status

Workout Logging P0

Offline-First Sync P0

Progression & Analytics P0

Indian-Food-First Nutrition P0

Targets & Habits P0

🧭 Product Vision

FORTIS aims to make fitness tracking fast enough for the gym,

practical enough for everyday nutrition, and reliable enough to work

without a network.

The core principle is simple:

Log less. Understand more. Progress consistently.

📌 Project Status

🚧 FORTIS is under active development.

The launch version focuses on the P0 feature set described above, with

additional capabilities planned for future releases.

👨‍💻 Development

Built with:

React Native · Expo · Firebase

📄 License

Add the project's license information here before publishing the

repository.
