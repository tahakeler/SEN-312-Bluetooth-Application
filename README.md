# SEN-312 Bluetooth Scanner Application
Author: Taha KELER
Course: SEN-312:00040 – App Development
Platform: Flutter (iOS only, tested on physical device)

---

## Project Description
This is a basic mobile app built with Flutter that scans for nearby Bluetooth Low Energy (BLE) devices. It fulfills the assignment requirement of scanning, listing, and running a mobile application on either simulator or real device. Since Bluetooth scanning does not work in simulators, this project is designed to run on a physical iPhone.

---

## Features
- Start BLE scan with a single button
- Show device name and identifier for each result
- Built using flutter_blue_plus package
- iOS support only (scanner requires real hardware)

---

## Technologies
Flutter version: 3.29.3
Plugin: flutter_blue_plus
Tooling: Dart SDK, Xcode 16.2, CocoaPods
Tested on: iPhone device with iOS 17+

---

## Setup and Run Instructions

1. Clone the repository

git clone https://github.com/tahakeler/SEN-312-Bluetooth-Application.git
cd SEN-312-Bluetooth-Application

2. Get Flutter dependencies

flutter pub get

3. Configure Bluetooth permission (iOS only)

Open file:
ios/Runner/Info.plist

Add this entry before </dict>:

<key>NSBluetoothAlwaysUsageDescription</key>
<string>This app requires Bluetooth access to scan nearby devices.</string>

4. Install CocoaPods dependencies

cd ios
pod install
cd ..

5. Open the project in Xcode

open ios/Runner.xcworkspace

6. Set up code signing

- In Xcode, go to Runner > Signing & Capabilities
- Select a valid Apple ID or Team
- Enable "Automatically manage signing"
- Make sure a real iPhone is connected via USB and selected as the target device

7. Build and run the app

Click the Run button in Xcode.
Allow Bluetooth permission on your iPhone when prompted.
The app will launch and display a "Start Scan" button.
Press it to scan and list nearby BLE devices.

---

## File Overview

lib/main.dart         # Application code
ios/Info.plist        # Bluetooth permission string
pubspec.yaml          # Dependencies
ios/Podfile           # iOS-specific dependency manager config

---

## Important Notes

- The iOS simulator cannot use Bluetooth. Use a real iPhone.
- All plugin permissions and configurations are handled in Info.plist and Podfile.
- Device name fallback is shown as 'Unknown' if unavailable.
- No UI animations or design, only core functionality.
- Built to match assignment criteria without unnecessary features.

## Authors:

Taha KELER