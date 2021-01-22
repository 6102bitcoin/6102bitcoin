# How to build samourai APK on linux (64 bit)

Get Dependancies 
- `sudo dpkg --add-architecture i386`
- `sudo apt-get update`
- `sudo apt-get install libc6:i386 libncurses5:i386 libstdc++6:i386 lib32z1 libbz2-1.0:i386`

Get Samourai Wallet Source Code
- `git clone https://code.samourai.io/wallet/samourai-wallet-android -b master`

Get Android Studio
- download [android studio .zip](https://developer.android.com/studio#downloads)
- extract the .zip file
- run ./studio.sh in a terminal in the android-studio/bin/ directory
- follow wizard

Build
- click open an existing project 
- select downloaded samourai wallet android source code
- Go to settings - Search and type `Android SDK`
- Go to SDK tools tab - Locate Version 29.0.3 - Toggle on and accept
- Go to build / build bundle(s) / APK(s) / Build APK(s)

Done, you will have an APK in `/samourai-wallet-android/app/build/outputs/apk/production/debug`
