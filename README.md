# HoloKitSDK v2 (Branch)

HoloKitSDK is the Unity plugins to build Mixed Reality apps for HoloKit. 

## What's New?  
* Jun 12, 2018. Added ARKit 2.0 + ARcore 1.3 support.
* Feb 23, 2018. Added ARKit 1.5 + ARcore 1.0 support.
* Jul 15, 2017. Added ARKit 1.0 support.
* Jun 1, 2017. Added VINS support. 

## Version Index
### HoloKit SDK v2.0 (Current version): 
* For ARKit 2.0 and ARCore 1.3, please checkout "v2.0" tag.

### HoloKit SDK v1.5: 
* For ARKit 1.5 and ARCore 1.0, please checkout "v1.5" tag.

### HoloKit SDK v1.0:
* For Google Tango, please checkout "v1.0_tango" tag.
* For Apple iOS (ARKit), please checkout "v1.0_ios" tag. 
* For Android (ARCore), please checkout "v1.0_android" tag. 

## Features 
### Stereoscopic rendering
### Calibration profile for different holoKits and phones
  * It's the key to have a correct HoloKit experience. Wrong calibration may lead to eye discomfort.
### AR/MR Mode Switch
  * You can easily switch between AR and MR mode. 
### Screen Brightness Control.
  * Make sure that the brightness of phone screen are the best for the current environment during the MR experience. 
### Universal wrapper for ARCore and ARKit.
  * HoloKit SDK integrates both ARCore and ARKit. It will seamlessly compile to Android and iOS devices. You don't need worry about the switch between platforms.
### Horizontal and vertical plane detection.
### Image marker detection and tracking.
### Local Multiplayer
Establish local player connection via Bluetooth + Wifi

## Requirements
### Hardware
* iOS (ARKit): iPhone 6S/6S+, 7/7+, 8/8+, X.
* Android (ARCore): Google Pixel 1/1XL/2/2XL, Samsung Galaxy S7/S7 Edge/S8/S8+/S9/S9+ and more on https://developers.google.com/ar/discover/supported-devices
### Software
* Unity 2018.2 or later with iOS and Android components installed. 
* iOS:
  * You must be an [Apple Developer](https://developer.apple.com/programs/). 
  * iOS 12.0 or later 
  * XCode 10 or later
* Android:
  * An Android device that supports ARCore 1.3 with Android version 8.0 or higher and installs ARCore 1.3 from Google Play Store. 
  * Android Studio 3.2 with Android SDK installed

## How to get started? 
### Setup (iOS)
1. Change the target platform to iOS and click Switch Platform.
2. Open "File" -> "Build Settings" and click "Build". 
3. Make sure that the parameters below is correct. 
Player Settings -> Other Settings
  * Architecture: ARM64
  * Camera Usage Description: "Blahblah...".
  * Target minimum iOS version: 12

### Setup (Android)
* An Android device that supports ARCore with Android SDK version 7.0 (API Level 24) or higher.
    * Prepare your device
    - Enable developer options
    - Enable USB debugging
* Android Studio with Android SDK installed.
* In your Unity configuration,  make sure you installed Android components.
    1. Change the target platform to Android and click Switch Platform.
    2. Click Player Settings to open the Android Player Settings. 
    3. Then change the following settings:
  - Other Settings > Minimum API Level: Android 8.0 or higher
  - Other Settings > Target API Level: Android 8.0 or 8.1
  - XR Settings > ARCore Supported: On

### Quick Start 
1. Import "HoloKitSDK" folder under "Assets" folder into a new Unity project.
2. Open the example scene "HoloKitSDK/Examples/HoloKitSample_ARKit".
3. Build your scene and run! This scene can run on both iOS and Android.
4. After the app runs, you should see a cube floating in the air somewhere. You may gaze at the sphere.
5. The app detects planes, and you may click on the screen to place the cube on the plane. 
6. You may touch the small "AR/MR" button to switch to HoloKit mode. 

### Create your own experience
1. Create a new scene in Unity. 
2. Drag and drop everything in "HoloKitSDK/Prefabs/Universal" to the scene.
3. Put anything you like under "HoloKitPlacementRoot", and your model should have a comparable size as "DebugCube". Then feel free to turn off or delete "DebugCube". 
4. Build your scene and run!
5. If you don't like the ambient light, please disable HoloKitAmbientLight in your scene.

## Reference 
### Prefabs
#### HoloKitCamera
* The most basic component to have your game responds to ARKit tracking. 
* It has a child VideoSeeThroughCamera that renders video seethrough VR experience. There are two extra cameras "Left Eye", "Right Eye" as its children, to render stereo for HoloKit. In "HoloKitCameraRig" object, you can set default see through mode and the key for toggling modes. 

#### HoloKitObjectGenerator

##### DisplayPlanes 
* To generate collidable planes when ARKit detects a plane. Optionally, you can set a Plane Prefab as its property to visualize the generated planes.

##### PointCloud
* To visualize point clouds that ARKit detects, for debugging purpose. 

##### AmbientLight
* A directional light, which intensity is controlled by ARKit. The intensity will adjust automatically based on the current environment's lighting in reality.

##### HoloKitPlacementRoot
* A convenient prefab to help you place your objects on the ground. See "How to place your object on the ground" for details.

#### HoloKitGazeManager
* A convenient prefab for you to emit gaze events. See "How to respond to gaze events" for details.

### How to place your object on the ground
1. Drag "HoloKitPlaneGenerator" and "HoloKitPlacementRoot" to your scene.
2. Put your object under "HoloKitPlacementRoot", and your object should have a comparable size as "DebugCube". Then feel free to turn off or delete "DebugCube".
    * ![Screenshot](images/whale.png)
3. Set the input key for placement.
    * ![Screenshot](images/place_key.png)

## Troubleshooting
### How to upgrade to iOS 12 Beta?
1. Backup your device. See "Prepare your device before you update to beta software" section in [About iOS beta software](https://support.apple.com/en-us/HT203282)
2. Follow [iOS beta Software Installation Guide](https://developer.apple.com/support/beta-software/install-ios-beta/) to install iOS 12 Beta.

### I don't have an Apple Developer account. 
You need one.

### I cannot see any "Team" in my XCode project settings.
Make sure "Automatically manage signing" is checked, and you've logged in with your developer account in "XCode" -> "Preferences" -> "Accounts". 

## Attribution
You shall read the [How to Attribute](https://holokit.io/#develop) section.

App developer shall mark with the words, "Works with HoloKit", or display either of the following two Holokit Logos in your app.

<img src="https://holokit.io/images/HoloKit_Logo1.png" width="250px">
or 
<img src="https://holokit.io/images/HoloKit_Logo2.png" width="90px">

For academic work, please cite Monocular Visual-Inertial State Estimation for Mobile Augmented Reality, P.Li et al (ISMAR 2017, accepted)

 
