# react-native--expo-shell-utils
React Native/Expo: A collection of command line scripts for working with QR codes, the browser, clipboard, emulator, etc.

by jaggz.h who is at gmail.com
2018-01-11

Currently two scripts are included:
---
# expo
Converts Expo Snack web URLS (https://) to the exp:// format
and copies the URL to the clipboard, using X11's xsel command,
which allows the Expo client, in the emulator, to pick it up.

Expo scripts for working with Expo snack URLs and QR Codes
for use with the emulator.

This script: expo

NOTE: Make sure you have clipboard sharing enabled in
      The Emulator -> ... -> Settings -> Clipboard sharing

Example input: https://snack.expo.io/HJVEgOugW
     Produces: exp://expo.io/@snack/H1cnedhBW
Example registered user input: (This doesn't work yet)
               https://snack.expo.io/@jaggzh/slider-example
     Produces: exp://expo.io/@jaggzh/slider-example
---
# expoqr
Examines the whole screen for a QR code (the one in the browser!)
Gets the URL from the QR code,
Converts it to an Expo app URL,
And copies it to the clipboard for Expo, in the emulator,
 to pick up in its main screen.

If found, the QR Code will contain, for example:
  exp://expo.io/@snack/Skf4bLBNz+BJDE-ISNz
Expo app wants:
  exp://expo.io/@snack/Skf4bLBNz

This script depends on:
 ImageMagick's "import" commandline utility (to capture the desktop)
  You may change the "import -window root ..." command to your own screen
  capture utility
 zbar-tools' "zbarimg" utility
  If you have another utility to scan an image for QR codes, be my guest

NOTE: Make sure you have clipboard sharing enabled in
      The Emulator -> ... -> Settings -> Clipboard sharing

