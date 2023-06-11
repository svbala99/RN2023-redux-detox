# React native - Boilerplate app bootstrapped in Typescript

A react native application with linting, husky and commitlint, Detox and REdux.

[![React Native](https://iili.io/HYGqeKQ.png)](https://reactnative.dev/)

## Tech stack

- React Native : For Cross platform mobile app development (iOS & Android)
- Node JS: For JS runtime environment
- Javascript : For application development
- Linting: eslint with commit hooks

## Packages used

| Package          | Version |
| ---------------- | ------- |
| React            | 18.x      |
| React Native     | 0.71.x  |

## To commit your code to repo

```
git add .
git commit
```

- It automatically stages all the local file changes, applies linting across the project folder, also does auto fixes, then will throw linting errors on the files if any.
- Kindly resolve them and then continue the same command: yarn commit
- Then it will ask few questions such as what type of commit it is, commmit msg, etc.
- Then after finishing it, finally do:

```
git push origin <branch_name>
```

## Instructions to front end engineers

- Raise MRs to development branch, create branches like: feat/CP3-5 from "development" branch
- If you want to make any global styling, do it at global level
- Same for constants, URLs, strings, etc
- Whenever you add an utility file, put it inside “utilities” folder
- Declare variables with “Be” form verbs or with aux verbs: isEmpty, hasElements, canClose, closesWindow
- Use camelCase for variables & methods
- Always prefer fat arrow functional components
- avoid underscore case for naming
- CapitalCase for JSX, camelCase for others
- use prettier
- Define actions with modularity & non-replicating
- Define entities in proper way (relevant items grouped together)
- Avoid onSuccess() methods on UI, everything should be handled in saga and reducer, not in UI
- Parallelize API calls whenever possible
- For reusable UI components : modularize them & make them reusable by passing corresponding props
- Remove unwanted / unused state variables
- Classify components (1. Presentational/ Dumb : just get the props and render, not connected to redux state 2. Containers: connected to redux state)
- Provide keys for iterable lists to avoid warnings
- all the actions should be handled in reducer (request, success, failure)
- Follow platform specific styles (fontweight : 600 for iOS, bold for Android in some places)
- Sort the imports : library imports first, followed by user imports, styles, constants, etc
- Implement safe area view to avoid clipping off in the notch-display type devices
- Add documentation whenever a new SDK / package is added
 
### Upgrade all dependency packages in a single shot
- yarn yarn-upgrade-all


### Run Android emulator Mac:-

```
cd ~/Library/Android/sdk/emulator
./emulator -list-avds
./emulator -avd {AVD_NAME}
```

### Run on iOS simulator

```
yarn ios:dev --simulator="iPhone 8"
yarn ios:dev --simulator="iPhone 8 Plus"
yarn ios:dev --simulator="iPhone 11"
```

### Delete Cache (Xcode)

```
rm -rf "${HOME}/Library/Caches/CocoaPods"
xcrun simctl delete unavailable
rm -rf ~/Library/Caches
rm -rf ~/Library/Developer/Xcode/Archives
rm -rf ~/Library/Developer/Xcode/DerivedData
rm -rf ~~/Library/Developer/Xcode/iOS Device Logs/
```

### Delete Device List (Xcode)

```
rm -rf  ~/Library/Developer/CoreSimulator/Devices/
If there is Unable to boot device error run,
xcrun simctl erase all
```

### Delete Cache (Android)

Go to android folder

```
./gradlew clean
./gradlew cleanBuildCache
```

\
## Installation

This App requires [Node.js](https://nodejs.org/) v10+ to run.

##### Download / clone the repo and install dependencies

```sh
git clone git@gitlab.com:cdhl/breathefree/breathefree-app-rn.git
cd breathefree-app-rn
yarn
```

##### Start the development server

```sh
yarn resetc
```

##### Install the app first time in Android (in Dev mode)

- Connect any Android device with USB
- Enable USB debugging in the device
- Accept to INSTALL the app when prompted during the deployment
- This command is not needed for subsequent changes made in project
- Whenever you include any package that impacts Android native, reinstall the app by issuing this command
- Alternatively the same can be achieved from Android Studio IDE by clicking "Run" button after opening "Android" project in it
- Supported Machines: Windows / Linux / Mac

##### Install the app first time in iPhones (iOS) - Dev mode

- Connect any iOS device with USB
- Enable USB debugging in the device
- Accept to INSTALL the app when prompted during the deployment
- This command is not needed for subsequent changes made in project
- Whenever you include any package that impacts Android native, reinstall the app by issuing this command
- Alternatively the same can be achieved from Xcode IDE by clicking "Build" & "Run" button after opening "iOS" folder in it
- Supported Machines: Mac only


- For more details: https://reactnative.dev/docs/signed-apk-android
  Note: If you run in Linux, issue ./gradlew instead of gradlew

## Output file location

You will find the APK file in:

```bash
~PROJECT_LOCATION\android\app\build\outputs\apk
```

## Install the released APK

```bash
adb install app.apk
```