*Please be aware that this application / sample is provided as-is for demonstration purposes without any guarantee of support*
=========================================================

# Integrating DataWedge into your Expo application

[Expo](https://docs.expo.io/) is a set of tools and services built around React Native that helps you develop, build, deploy and quickly iterate on cross platform applications using JavaScript or TypeScript.

We get occasional questions from our developer community how to write an Expo application targeting Zebra Android devices so I put together this unofficial sample.  This sample uses DataWedge which is the recommended way to capture data - If you just want to run the sample jump to the Installation / quick start section below.

## Using Expo with DataWedge

Anyone new to Expo will quickly come up against the "Managed workflow" vs. "Bare workflow" way of working.  Expo has good documentation on the [differences between the two](https://docs.expo.io/introduction/managed-vs-bare/) and it is important to understand the differences because **you can only interface with DataWedge using the 'Bare workflow'** 

DataWedge exposes an [Intent-based API](https://techdocs.zebra.com/datawedge/latest/guide/api/) which uses Broadcast Intents to control the scanner and provides the ability to listen for scan events via Intent.  The [IntentLauncher API](https://docs.expo.io/versions/v40.0.0/sdk/intent-launcher/) provided to 'managed' expo applications is not functional enough to interface with DataWedge, therefore a [different ReactNative plugin](https://www.npmjs.com/package/react-native-datawedge-intents) is required. 

- `expo init <myApp>`
- One of the bare workflow options, e.g. `'bare and minimal, just the essentials to get started'`
- `cd <myApp>`
- `yarn add react-native-datawedge-intents`

## Demo

There already exists an unofficial [ReactNative sample](https://github.com/darryncampbell/DataWedgeReactNative) for Zebra Android devices so I thought it would be worthwhile converting that to an Expo app.  The Expo documentation has a section for [converting an existing ReactNative app to Expo](https://docs.expo.io/bare/installing-unimodules/) as well as a [walkthrough of the bare workflow](https://docs.expo.io/bare/exploring-bare-workflow/), so I followed those:

1. Cloned existing https://github.com/darryncampbell/DataWedgeReactNative project, made a copy of it in this repository and changed all references from 'ReactNative' to 'Expo' 
2. `yarn add react-native-unimodules`
3. **Important:** Followed the instructions at https://docs.expo.io/bare/installing-unimodules/ to update my project
4. `yarn install`
5. I chose to add a script to my `package.json` to point `yarn android` to `react-native run-android` as the old DataWedgeReactNative project did not use yarn.
6. I wanted to show some use of the Expo SDK so I chose [Device](https://docs.expo.io/versions/v40.0.0/sdk/device/).
7. `expo install expo-device`
8. Modified the existing application to use the Expo Device API to print the device manufacturer at the top of the app

*View this application running by following the installation / quick start section immediately below:*

## Installation / Quick Start
Assuming you have an [Expo environment](https://docs.expo.io/get-started/installation/) configured
* `git clone https://github.com/darryncampbell/DataWedge-Expo-Sample.git`
* `cd DataWedge-Expo-Sample`
* `cd DataWedgeExpo`
* `yarn install`
* `yarn android`

**If you receive `Task :app:validateSigningDebug FAILED` then please see [this StackOverflow post](https://stackoverflow.com/questions/57104357/react-native-task-appvalidatesigningdebug-failed)**

![Expo](https://raw.githubusercontent.com/darryncampbell/DataWedge-Expo-Sample/main/screenshots/002.jpg)