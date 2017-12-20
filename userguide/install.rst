Install Ubuntu Touch
====================

There are many ways to install Ubuntu Touch on your supported device. To check if your device is supported, check `this page <https://ubports.com/page/fs-flash-phone>`_

Back up your data
-----------------

Your data on your phone is important. You don't need to lose it in the upgrade. 

If you're already using Ubuntu Touch on your phone and any distro that supports snaps on your PC, use the `magic-device-tool <https://github.com/MariusQuabeck/magic-device-tool>`_ to back up your device.
    
Non-Canonical devices
---------------------

These instructions will help you install our OS on the "Core Devices" such as the Nexus 5 or Fairphone 2.

Switch from Android to Ubuntu Touch
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install ADB drivers on computer
-------------------------------

To get adb working on your **windows** pc, follow `this guide <https://forum.fairphone.com/t/pencil2-adb-on-the-fairphone-2-windows-driver/11529>`_.

To get adb working on your **linux** pc, follow `those <https://ubports.com/forum/wiki-2/question/how-to-use-adb-from-ubuntu-desktop-3>`_ instructions::

    sudo apt-get install android-tools-adb android-tools-fastboot
    
First you have to install ubuntu-phablet-tools::

    sudo apt-get install phablet-tools
    
Than you have to add your device to your desktop. In my case for the Fairphone 2::

    echo "0x2ae5" > ~/.android/adb_usb.ini
    
Even if you own a One Plus One (OPO) you have to do add it::

    echo "0x9d17" >> ~/.android/adb_usb.ini
    
Other devices don't need to be added manually.

Then you have to kill the adb server::

    adb kill-server


Enable developer mode and USB debugging on device
-------------------------------------------------

Go to settings, scroll all the way down to About this device (or about this phone) select that, scroll down to build number, and start tapping that fast over and over until it says you've unlocked developer.
Then go back up one level and now there is a new menu option called options for developers. Select that, then scroll down to USB debugging, switch that on.

When you plug the USB cable, change the USB mode to MTP (default was charge only). Look at your device screen : you should see a pop-up asking if you trust the fingerprint of your computer. After accepting that, it shouldn't be "unauthorized" anymore.

Now adb should work on your phones side. 
Check if you see it correctly from your computer: with "adb devices" you get your device listed.

* On Linux, Windows or MacOS: Use the `UBports GUI installer <https://github.com/ubports/ubports-installer/releases>`_

Official "Ubuntu for Devices" devices
-------------------------------------

These instructions will help you install to a device that ran an official Canonical build of Ubuntu for Devices, such as the BQ M10 or Meizu MX4

Switch from Canonical builds to UBports builds
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* On any Linux distro with Snaps: Use the `magic-device-tool <https://github.com/MariusQuabeck/magic-device-tool>`_. Please read the instructions carefully!
* On Windows or MacOS (**beta**!): Use the `UBports GUI installer <https://github.com/ubports/ubports-installer/releases>`_

Switch from Android to Ubuntu
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

BE VERY CAREFUL! This can permanantly damage or brick your device. NEVER check the "Format All" option in SP Flash Tool and carefully read everything that it tells you. Some users have destroyed the partition that holds their hardware IDs and can no longer connect to Wi-Fi or cellular networks.

* BQ devices: Download the official Ubuntu Edition firmware from `here <http://www.mibqyyo.com/en-download/>`_ and use SP Flash Tool to flash it.
* Meizu devices: You are pretty much stuck on Flyme. For the MX4, there are some instructions floating around for downgrading your OS, gaining root with an exploit, unlocking your bootloader, and so on. We aren't going to link to them here for obvious reasons. The Pro5 is Exynos-based and has its own headaches. You're even more at your own risk on these.

We are being vague with these instructions on purpose. While we appreciate that lots of people want to use our OS, flashing a device with OEM tools shouldn't be done without a bit of know-how and plenty of research. People have destroyed their phones.
