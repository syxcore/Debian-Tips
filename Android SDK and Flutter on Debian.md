# Android SDK Command-Line Tools Setup on Ubuntu

This guide shows you how to install the Android SDK and command-line tools on Ubuntu without using Android Studio.

## Prerequisites
- Ubuntu or a Debian-based Linux distribution
- Terminal access

## Installation Steps

### 1. Update Your Package List
```bash
sudo apt update
```

### 2. Install Required Dependencies
```bash
sudo apt install unzip wget
```

### 3. Download Command-Line Tools
```bash
wget https://dl.google.com/android/repository/commandlinetools-linux-10406996_latest.zip -O commandlinetools.zip
```

### 4. Create SDK Directory
```bash
mkdir -p ~/Android/Sdk/cmdline-tools
```

### 5. Unzip Downloaded Tools
```bash
unzip commandlinetools.zip -d ~/Android/Sdk/cmdline-tools
```

### 6. Rename the Unzipped Folder
```bash
mv ~/Android/Sdk/cmdline-tools/cmdline-tools ~/Android/Sdk/cmdline-tools/latest
```

### 7. Add Tools to PATH
Edit your .bashrc file:
```bash
nano ~/.bashrc
```
Add the following lines at the end:
```
export ANDROID_SDK_ROOT=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_SDK_ROOT/cmdline-tools/latest/bin
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
```
Apply the changes:
```bash
source ~/.bashrc
```

### 8. Verify Installation
```bash
sdkmanager --version
```

### 9. Install Essential SDK Packages
```bash
sdkmanager "platform-tools" "platforms;android-30" "build-tools;30.0.3"
```

## Done!
You’re now ready to use the Android SDK command-line tools. Happy coding!

