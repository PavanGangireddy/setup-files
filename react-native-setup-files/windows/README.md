# Running react-native app in windows

## 1. [Installing node and npm](https://tap.ibhubs.in/revision/node-setup/)

## 2. Install Java Development Kit

### 2.11 Get the latest version from corresponding folder

### 2.12 Go through this [link](https://docs.oracle.com/en/java/javase/11/install/installation-jdk-microsoft-windows-platforms.html#GUID-BCE568C9-93D3-49F4-9B0C-9DD4A3419792)

- Running the JDK Installer
- Setting the PATH Environment Variable
- Now verify java installation
  ```sh
  javac -version
  ```
- It should output - `javac 11.0.7`

## 3. Install Android Studio

> Manually

### 3.11 Get the latest version from corresponding folder

### 3.12 Follow the below url

- [Link](https://developer.android.com/studio/install#windows)

### 4. Preparing AndroidDevice

- You will need to have Android device to run your ReactNative App. It can be either a physical or virtual Android device.

### 4.1 Physical Device [Skip this if you are doing for first time]

- For running app for the physical device you will need to Enable Debugging over USB and Plug in your device via USB

### 4.2 Virtual Device (emulator)

- To do that open the android studio and create a virtual device and power up AVD.
- [Create a Virtual device](https://developer.android.com/studio/run/managing-avds)
- Run it

### 4.3 Verifying device is connected or not run this command

- After running this command list of connected devices will display on terminal

  ```sh
  adb devices
  ```

## 5. Install react-native, create project and run the app

- Install react-native-cli using npm.

  ```sh
  npm install -g react-native-cli
  ```

- Create react-native project via react-native-cli.

  ```sh
  react-native init myApp
  ```

- Finally run your react-native project.

- Move to created project dir.
  ```sh
  cd myApp   // Start react-native packager
  npm start  // open up another terminal and run android
  react-native run-android
  ```

# Troubleshoot
