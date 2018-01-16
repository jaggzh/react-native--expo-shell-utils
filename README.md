# `react-native--expo-shell-utils`

## React Native/Expo command line scripts

**A collection of command line scripts for working with
[Expo Snacks'](https://snack.expo.io/):<br />
QR codes, the browser, clipboard, emulator, etc.**<br />
by jaggz.h who is at gmail.com. Script version date: 2018-01-16

References:
1. React Native: https://facebook.github.io/react-native/
2. Expo: https://expo.io/
3. Expo Snacks: https://snack.expo.io/

## Currently two scripts are included:

---

# expo
Converts Expo Snack web URLS (https://) to the exp:// format
and copies the URL to the clipboard, using X11's xsel command,
which allows the Expo client, in the emulator, to pick it up.

Expo scripts for working with Expo snack URLs and QR Codes
for use with the emulator.

NOTE: Make sure you have clipboard sharing enabled in
      The Emulator -> ... -> Settings -> Clipboard sharing

Example: `expo https://snack.expo.io/HJVEgOugW`<br />
Produces: `exp://expo.io/@snack/H1cnedhBW`

Example registered user input (this may not work yet):<br />
 `expo https://snack.expo.io/@jaggzh/slider-example`<br />
Produces: `exp://expo.io/@jaggzh/slider-example`

---

# expoqr
Examines the whole screen for a QR code (the one in the browser!)<br />
Gets the URL from the QR code,<br />
Converts it to an Expo app URL,<br />
And copies it to the clipboard for Expo, in the emulator,</br />
 to pick up in its main screen.

### To run:

1. Have QR code visible on screen (in browser probably)
2. Run: `expoqr`

If found, the QR Code from Expo's snacks will contain, for example:<br />
  `exp://expo.io/@snack/Skf4bLBNz+BJDE-ISNz`<br />
Then, then clipboard will have what the Expo app craves:<br />
  `exp://expo.io/@snack/Skf4bLBNz` will be placed in the clipboard (currently uses xsel -ib, so it only works in un\*x/X11)

### This script depends on:<br />
* ImageMagick's "`import`" commandline utility (to capture the desktop)<br />
  *You may change the "`import -window root ...`" command to your own screen*
  capture utility
* zbar-tools' "`zbarimg`" utility<br />
  *If you have another utility to scan an image for QR codes, be my guest.*

### To install those in Debian/Ubuntu:
* sudo apt install imagemagick zbar-tools

NOTE: Make sure you have clipboard sharing enabled in
      The Emulator -> ... -> Settings -> Clipboard sharing

