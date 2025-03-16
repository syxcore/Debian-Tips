# Android SDK Installation Guide on Debian Linux

## Prerequisites
- Debian Linux
- Basic command-line knowledge
- Sudo privileges

## Step 1: Download Command-line Tools
Download the latest Android SDK command-line tools from the official website:
```bash
wget https://dl.google.com/android/repository/commandlinetools-linux-9477386_latest.zip
```

## Step 2: Extract the Tools
Unzip the downloaded file to your preferred installation directory (e.g., `/opt/android-sdk`):
```bash
sudo mkdir -p /opt/android-sdk/cmdline-tools/latest
sudo unzip commandlinetools-linux-9477386_latest.zip -d /opt/android-sdk/cmdline-tools/latest
```

## Step 3: Set Up Environment Variables
Add the following to your shell profile (e.g., `~/.bashrc` or `~/.zshrc`):
```bash
export ANDROID_HOME=/opt/android-sdk
export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```
Apply the changes:
```bash
source ~/.bashrc
```

## Step 4: Accept SDK Licenses
To accept licenses, run:
```bash
sdkmanager --licenses
```
If you encounter errors related to permissions, change the ownership of the SDK directory:
```bash
sudo chown -R $USER:$USER /opt/android-sdk
```

## Step 5: Install Essential Packages
Install necessary Android components:
```bash
sdkmanager "platforms;android-34" "build-tools;34.0.0" "platform-tools" "emulator" "system-images;android-34;google_apis;x86_64"
```

## Troubleshooting
### Error: Failed to read or create install properties file
This error usually occurs due to permission issues. Fix it by running:
```bash
sudo chown -R $USER:$USER /opt/android-sdk
```
Then retry the installation command without sudo.

## Verifying the Installation
List installed components to ensure everything is properly set up:
```bash
sdkmanager --list
```

## Additional Tips
- Always use the latest version of command-line tools.
- Check environment variables if any component is not recognized.

