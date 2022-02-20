# Big Sur
- BIG SUR HAS BEEN RELEASED https://github.com/tlefko/XPS-13-9350-Big-Sur
- Full functionality
- Using Clover Bootloader
- Complicated initial install but works flawlessly
# Site
- checkout our official site! https://twortech.wixsite.com/pcmac

# News
- In light of the recent WWDC, we will begin testing the functionality of our EFI on macOS 11 for this device with the latest developer preview

# Version Info

This build is compatible up to Catalina 10.15.4 (before supplemental update)
- Now Compatible with 10.15.5
- Please leave feedback with issues or w/o
- Comitted to Updating up to OS 11
- MULTITOUCH TOUCHSCREEN SUPPORT

# Latest Release Notes
- Fixed Bluetooth and Wifi Stability Issues
- Improved Preformance and Power Managements
- Can Provide Files for Display Overrides
- Additional Patches for 3K Display
- updated for 15.4 rev 1
- if using unsupported wifi card disable it in bios
- use config.plist not HD520
- Perfect Sleep/Wake for 1080P Model no-touch, still bugs for 3K
# Sleep Bugs
- plugging or removing usb c device after sleep will put computer back to sleep (3K Display Only)
# POST

- run sudo pmset -a hibernatemode 0

# Description

- This esentially an ultra-simplistic version that is stable without the use of a deploy or complicated file installations and copies.
- You can easily view all the SSDT patches along with configuration files for the bootloader as they are all documented clearly in the files.
- This does include a copy of Clover, which of course I do not contribute to and am only responsible for the provided files, patches, and kext placements

This guide provides a working setup with little knowledge of the topic and without "optimization" (because often they can break things). But, it is fully functional and preforms properly and is stable
- Make sure you are using DW1560 for wifi or else KP. If not using remove BRCM kexts from CLOVER>kexts>other

# Styling
- This guide is designed to be literally as thorough as possible to appeal all types of users.  It does not cover complex topics like undervolting etc etc only to provide a completely functional system

# Notes
- Never tested USB C except for charging, works great
- USB devices eject on sleep (not really an issue)
- 4K model has minor sleep wake issues occasionally, 1080P is fully functional
- 4K sleep has been heavily improved however and glitches are rare, fixed by reopening lid

# BIOS Setup
-  Set all SATA operation as AHCI
- Disable Secure Boot, Fast Boot
- For Coil Whine improvement disable C-States
- Enable UEFI Booting

# Recommended: Clean Install (Preinstall steps)
- Format a USB (16GB) as Journaled and then proceed to download the latest Catalina Installer Patcher Application
- Download the latest Catalina installer from within the Patcher App, and select to download a new copy and install to your USB device
- Download the clover configurator application and mount the EFI of the USB partition, then copy the contents of the Files linked above to A new EFI Folder (that you create) within the EFI partition.

** This is because the App Store installers will often not download a full installer, just an truncated version that downloads the installer files from the interent while installing. Thus, they're not bootable from a USB as they're not complete. That is why you should use this method to make sure the installer is usable for bootable media.

# Install Steps
 - Simply use F12 to boot from the USB device, and select the USB Device and then boot from the Install mac OS partition. I have defaulted the installer to boot into verbose mode so I can easily see the errors you guys are seeing if you encounter them. If everything goes well, you can disable these from the boot arguments selection of Clover Configurator
 - Boot into the USB Device, and follow the steps to format your SSD from the installer to install Mac OS Catalina. *Note* the trackpad will not function at this point, but the touchscreen will. This is caused by the way the installer handles Kext loading but because the touchscreen is being loaded via usb and the keyboard in a different method (which I can explain in detail if you'd like, the install will be possible.
 - Do not be alarmed if the installer takes a long time to boot into, this is expected
 - Once you have done this step, use F12 to select the USB and boot into the installer from the SSD in the options menu. (you cannot boot natively yet as the EFI isn't copied into the SSD yet.
 - Setup computer as normal, touchpad, brightness, etc, should all be functioning at this point. Same with wifi. Then, you should using Clover configurator copy the contents of the USB EFI into the EFI folder of your SSD EFI partition (in the folder)
 - Now we will add this as a native boot option.
 - Setup computer as normal, touchpad, brightness, etc, should all be functioning at this point. Same with wifi. Then, you should using Clover configurator copy the contents of the USB EFI into the EFI folder of your SSD EFI partition (in the folder)
 - Now will we add this as a boot entry so you can always boot from this natively without the USB.
 
 # Boot Entry Setup
 - Boot into the BIOS of the computer, then navigate to the Boot setup (or entries (not sure what it is called exactly, but it will be a list of the options your computer selects to boot)
 - Click add new, and make sure the USB isn't plugged in.
 - Select the only option that is avaiable, and in FS0 navigate to Boot/BOOTx64. Add this as an entry, then select this as whatever priority you would like.
 
 # Credits
- Original kext authors
- Clover
 
 # Messages and Facetime
 - Gnerate your own Serials, Board Numbers, MLB
 - There are various guides online to do this and as default they're set to essentially Null (Fakeserial)
 - This is fairly straightforward and there is lots of external recourses, or you can contact me for support.
 # Headphones and Audio
 - All audio from speakers should work perfectly along with Bluetooth and USB audio
 - To resolve headphones static issue (wired) install combojack 
 
 # Finished!
 - Congratulations, there really aren't any more steps that are required. Feel free to contact me with any questions. 

# Donations 
- ***Send me a coffee***
- https://www.paypal.com/donate/?business=LG87NZSPQGFMS&no_recurring=0&currency_code=CAD
