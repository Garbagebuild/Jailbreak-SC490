🔧 Requirements
SC490 phone (unlocked bootloader)

A PC with ADB & Fastboot, or WebADB

system.img ready to flash (includes apps > Chess & a Web Browser) https://drive.google.com/file/d/1EYa8X401p5NOE4jUnKPhjEA1KbM5LoTn/view
NOTE: if this bricks your phone the stock system.img is here https://github.com/Garbagebuild/SC490-Jethro-Firmware along with all other partitions.
Macrodroid pre-installed in the image

Optional: External keyboard for easier navigation

🛠️ Instructions
Step 1: Enable Developer Options and USB Debugging
Boot the phone normally.

Go to Settings > System > About Phone

Scroll down to Build Number and tap it at least 7 times (until it says "You are now a developer!")

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

A list of compatible apps that work on this phone

🕹️ If anyone finds a working GBA Emulator apk that is compatible with this phone, I will give you a big wet kiss.

