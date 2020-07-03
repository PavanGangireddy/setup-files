## 1. [Installing node and npm](https://tap.ibhubs.in/revision/node-setup/)
## 2. Install Java Development Kit
- Run the below command
    ```sh
    sudo apt install openjdk-11-jdk -y
    ```
- Now verify java installation
    ```sh
    javac -version
    ```
- It should output - `javac 11.0.7`

## 3.  Install Android Studio 

> Manually

### 3.11 Download latest version 

- [Link](https://developer.android.com/studio)

### 3.12 Follow the below url

- [Link](https://developer.android.com/studio/install#linux)

### 3.13 Configure build path in your .bash_profile

- Go to terminal and run command

    ```sh
    $HOME/.bashrc 
    ```
- Now on file will open in terminal copy the below line and save the file

    ```sh
    export ANDROID_HOME=$HOME/Android/Sdk
    export PATH=$PATH:$ANDROID_HOME/tools
    export PATH=$PATH:$ANDROID_HOME/tools/bin
    export PATH=$PATH:$ANDROID_HOME/platform-tools
    export PATH=$PATH:$ANDROID_HOME/emulator
    ```

- Proceed to step 4.
> Using Command line

### 3.21 Using android-studio repository

- We need to add android studio official repository to the sources list. Therefore, Type the below command to add.
Hit enter when it ask for the confirmation.
    
    ```sh
    sudo add-apt-repository ppa:maarten-fonville/android-studio
    ```
- Now update apt cache.
    
    ```sh
    sudo apt update
    ```
    
- Now install android studio using apt. So that it will install the software along with dependencies.

    ```sh
    sudo apt install android-studio 
    ```

### 3.22 Configure VM acceleration on Linux

- Linux-based systems support VM acceleration through the KVM software package. 
- Requirements
    - Running KVM requires specific user permissions. Make sure that you have sufficient permissions as specified in the KVM installation instructions.
- Check whether KVM is currently installed on Linux
    - You can use the emulator -accel-check command-line option to check whether you have KVM installed. Alternatively, you can install the cpu-checker package containing the kvm-ok command.

- The following example shows how to use the kvm-ok command:

    ```sh
    sudo apt-get install cpu-checker
    egrep -c '(vmx|svm)' /proc/cpuinfo
    12
    kvm-ok
    INFO: /dev/kvm exists
    KVM acceleration can be used
    ```

- Use the following command to install KVM in linux:

    ```sh
    sudo apt-get install qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils ia32-libs-multiarch
    ```

### 4. Preparing AndroidDevice

- You will need to have Android device to run your ReactNative App. It can be either a physical or virtual Android device.

### 4.1 Physical Device

- For running app for the physical device you will need to Enable Debugging over USB and  Plug in your device via USB

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

# Reference
- [Installation](https://www.krizna.com/ubuntu/install-android-studio-ubuntu-20-04)
- [Troubleshooting](https://medium.com/dooboolab/running-react-native-app-in-ubuntu-18-04-7d1db4ac7518)

# Running react-native app in windows



# Troubleshoot

1. When facing below error,
    ```
    Error: System limit for no of watchers reached in vscode:
    ```
- solution: run below commands in terminal.

    ```sh
    echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
    ```

2. Trouble shooting with permission
- Sometimes there is permission issue running device telling to 
    grant permisson on `/dev/kvm`.

    ```sh
    sudo apt install qemu-kvm
    sudo adduser <your username> kvm
    sudo chown <your username> /dev/kvm
    ```
