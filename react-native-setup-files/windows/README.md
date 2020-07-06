# Running react-native app in windows

## 1. [Installing node and npm](https://tap.ibhubs.in/revision/node-setup/)

> Note: If you have already installed node, skip this step

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

### 3.13 Configure the below build paths in your system variables, PATH variable

### Set the Android SDK Home Environment Variable

To set the Android SDK home environment variable, do the following:

1. Click Start.
2. Right-click Computer, and then select Properties.
3. Click Advanced system settings.
4. On the Advanced tab, click Environment Variables.
5. Under User variables, click New.
6. For Variable name, type the following value:
   `ANDROID_HOME`
7. For Variable value, type the path to the parent directory where your Android SDK is installed. For instance:
   ```sh
   C:\Android\android-sdk
   ```
8. Click OK until you have closed all dialog boxes. Do not click Cancel.

### Manually Set the Android Environment Variables

To manually set the Android environment variables for a Windows computer, do the following:

1. Click Start.
2. Right-click Computer, and then select Properties.
3. Click Advanced system settings.
4. On the Advanced tab, click Environment Variables.
5. Under System Variables, double-click Path.
6. Add to the Path variable the location of the /bin folder in your installation of the JDK. For example:
   ```sh
   C:\Java\jdk1.7.0_79\bin
   ```
7. Add to the Path variable the locations of the /emulators, /tools, and /platform-tools folders in your installation of the Android SDK.
   -For example:

   ```sh
   C:\Android\android-sdk\emulator; C:\Android\android-sdk\tools;C:\Android\android-sdk\platform-tools
   ```

8. Click OK until you have closed all dialog boxes. Do not click Cancel.

### 4. Preparing AndroidDevice

- You will need to have Android device to run your ReactNative App. It can be either a physical or virtual Android device.

### 4.1 Physical Device [Skip this if you are doing for first time]

- For running app for the physical device you will need to Enable Debugging over USB and Plug in your device via USB

### 4.2 Virtual Device (emulator)

- To do that open the android studio and create a virtual device and power up AVD.
- [Create a Virtual device](https://developer.android.com/studio/run/managing-avds) - Select Build tools -> APILevel 28 Pie device
- Select Build tools - APILevel 28 Pie device
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
