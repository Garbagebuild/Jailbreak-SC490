If your looking for temporary root on this phone go to https://github.com/Garbagebuild/TWRP-for-Jethro

🔧 Requirements
SC490 phone (unlocked bootloader)

A PC with ADB & Fastboot, or WebADB

system.img ready to flash (includes apps > Chess & a Web Browser) https://drive.google.com/file/d/1EYa8X401p5NOE4jUnKPhjEA1KbM5LoTn/view



NOTE: if this bricks your phone the stock system.img is here https://github.com/Garbagebuild/SC490-Jethro-Firmware along with all other partitions.






🛠️ Instructions
Step 1: Enable Developer Options and USB Debugging
Boot the phone normally.

Go to Settings > System > About Phone

Scroll down to Build Number and tap it until you are satisfied or at least 7 times (until it says "You are now a developer!")

Now go to Settings > System > Developer Options

Enable OEM Unlocking.

IMPORTANT: Scroll down and enable USB Debugging.

Connect your phone to your PC. When the popup appears:
👉 "Allow USB debugging from this computer?"
✔️ Tap Always allow, then OK.

Step 2: Flash the Custom System Image
Go to https://app.webadb.com/shell or use your own ADB terminal.

Type:

adb reboot bootloader
Once the phone enters Fastboot mode, type:

fastboot flash system system.img
⏳ This may take a few minutes. Be patient.

After flashing completes, type:

fastboot reboot
Step 3: Launch Macrodroid Using Mouse Mode
Once rebooted, wait for notifications to appear.

Press the red "Home" button, then press Up on the D-Pad to view notifications.

Tap the Macrodroid notification to open the app.

🔒 Macrodroid is used to launch any app via custom buttons or triggers.

Now hold down the * (asterisk) key until a mouse pointer appears on screen.

Use this pointer to interact with Macrodroid. (it also comes in handy using 3rd party apps!)

Step 4: Set Up a Floating Button to Launch Apps
In Macrodroid, go to the "Macros" tab.

Tap the + (plus) icon to create a new macro.

Under Triggers, tap the + (plus) icon again.

Scroll down to User Input → select Floating Button
(You might need the mouse pointer to tap this.)

For best results:

Set the "Fixed button" option

Adjust both button placement options

Tap OK

Now under Actions, tap the plus:

Choose Applications

Select Launch Application

Pick the App Launcher (orange icon)

Name your macro (e.g., “App Button”) and save it.

Tap the settings gear icon in the top-right using the mouse pointer — this will launch your chosen app.

🎉 Boom! You’ve got app access.

🔜 Coming Soon
A tutorial on how to add your own apps into the system.img
--------------------------------------------------------
Most apps that don’t require Google Play Services will run fine on this phone.
However, if an app contains native `.so` library files, those libraries must be placed in:

/system/app/MyApp/lib/arm/*.so

Doing this manually can be tedious — that’s why there’s now a tool to automate it.

If install2.0.bat causes problems (for example, it stops after extracting the libraries), use install.bat instead.
install.bat requires you to tell it which CPU architecture your APK uses.

How to Find Your APK’s Library Architecture:
1. Make sure 7-Zip is installed (required for the script to work).
2. Right-click your APK file and open it with 7-Zip (or any zip extractor).
3. Open the `lib` folder inside the APK.
4. You should see a folder named either:
   - armeabi
   - armeabi-v7a
5. Note which one exists — this is your architecture.

Editing the Script for the Correct Architecture:
1. Right-click on install.bat and choose Edit (Notepad will open).
2. In Notepad, go to the Edit menu and click Find.
3. Search for: armeabi-v7a
4. If your APK has only armeabi (and does not have armeabi-v7a),
   replace all instances of armeabi-v7a with armeabi
5. Save the file and close Notepad.

Installing the App:
1. Connect your phone via USB with USB Debugging enabled.
2. Run install.bat.
3. Enter the full path to your APK when prompted.
4. The script will:
   - Push the APK into /system/app/<YourAppName>/
   - Extract and place the `.so` libraries into /system/app/<YourAppName>/lib/arm/
5. Reboot your device to apply the changes.

Note: This process requires root access and a writable /system partition.
If /system is read-only, remount it as read/write or use Magisk to create a systemless install.


