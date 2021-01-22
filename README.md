# DataWedge-Expo-Sample
Sample application written with the Expo framework to show barcode scanning on Zebra mobile computers 

Notes:
- https://github.com/darryncampbell/react-native-datawedge-intents/issues/14
- https://docs.expo.io/bare/exploring-bare-workflow/
- expo init DataWedgeExpo
- I selected 'bare and minimal, just the essentials to get started'
- cd DataWedgeExpo
- yarn add react-native-datawedge-intents
- yarn android (to run)

NEW PLAN
- Add some expo functionality to the existing DataWedge React Native sample
- Cloned existing DataWedgeReactNative sample
- yarn add react-native-unimodules
- yarn install replaces npm install
- Had to add to my package.json an android script, "react-native run-android"
- Had to add my debug.keystore to DataWedgeExpo\android\app
- To demo Expo SDK will use https://docs.expo.io/versions/v40.0.0/sdk/device/
- expo install expo-device
- Device manufacturer is returning NULL... I needed to follow https://docs.expo.io/bare/installing-unimodules/

todo:
Create blog - main point is you need to use the bare workflow because the Intent API offered by Expo does not have enough functionality to control the DataWedge API.  ALSO, KNOWN ISSUES 