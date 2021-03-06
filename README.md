
# :fire:react-native-lit:fire:

A React Native module to access camera flashlight for Android and iOS apps like:

iOS | Android
------- | ----
![ios-back](/images/lit-iphone.png) | ![android-back](/images/lit-android.png)

## Table of contents
- [Install](#Install)
- [Usage](#usage)

## Install

`$ npm install react-native-lit --save`

### Mostly automatic installation

`$ react-native link react-native-lit`

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-lit` and add `RNLit.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNLit.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNLitPackage;` to the imports at the top of the file
  - Add `new RNLitPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-lit'
  	project(':react-native-lit').projectDir = new File(rootProject.projectDir,'../node_modules/react-native-lit/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-lit')
  	```

## Usage
Checkout the Example app.
```javascript
import RNLit from 'react-native-lit';
...
RNLit.isFlashAvail()
  .then(result => {
    if (result.deviceSupportsFlash) {
      return RNLit.turnOn(true);
    }
  })
  .then(result => {
    this.setState({isOn: true});
  })
  .catch(error => {console.log(error)});
...
```
