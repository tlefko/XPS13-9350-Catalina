
# Description
- This  esentially an ultra-simplistic version that is stable without the use of a deploy or complicated file installations and copies.
- Many files and ideas are sourced from @maz-1, @syscl, and my previous guides
- Granted, many files are similar or the same but there is significantly less of them and/or they are predeployed into spots where they will work just as well, even if not as efficient on bootup.
- Esentially, this guide is designed to provide a perfectly working setup with little knowledge of the topic and without optimization (because often they can break things). Most patches on the main plist use patches implemented by him as well.

****This guide does work excellently however and will provide you with a near perfect setup for Catalina for your XPS 9350, and is currently my daily driver as I struggled using the referenced users files as well.

# Styling
- This guide is designed to be literally as thorough as possible to appeal to those who really don't understand many of the things in @maz-1's guide or some of the other users as they assume you would already understand this information. It does not cover complex topics like undervolting etc etc

# Notes
- Never tested USB C except for charging, works great
- no issues with sleep, wakeup.
- power management is defaulted as I found with @maz-1 it had issues when on battery switching from AC
- USB devices eject on sleep (not really an issue)
- Haven't implemented a Bluetooth solution into this yet, as I don't really use it -- will be added ASAP (I believe
- KILLER WIFI will NOT work, must use one of the supported chipsets  (DW1560 is excellent)

# BIOS Setup
-  Set all SATA operation as AHCI
- Disable Secure Boot, Fast Boot
- For Coil Whine improvement disable C-States
- Enable UEFI Booting

# Recommended: Clean Install (Preinstall steps)
- Format a USB (16GB) as Journaled and then proceed to download the latest Catalina Installer Patcher Application
- Download the latest Catalina installer from within the Patcher App, and select to download a new copy and install to your USB device
- Download the clover configurator application and mount the EFI of the USB partition, then copy the contents of the Files linked above to the EFI Folder within the EFI partition.

** This is because the App Store installers will often not download a full installer, just an truncated version that downloads the installer files from the interent while installing. Thus, they're not bootable from a USB as they're not complete. That is why you should use this method to make sure the installer is usable for bootable media.

# Install Steps
 - Simply use F12 to boot from the USB device, and select the USB Device and then boot from the Install mac OS partition. I have defaulted the installer to boot into verbose mode so I can easily see the errors you guys are seeing if you encounter them. If everything goes well, you can disable these from the boot arguments selection of Clover Configurator
 - Boot into the USB Device, and follow the steps to format your SSD from the installer to install Mac OS Catalina. NOTE THE TRACKPAD WILL NOT FUNCTION AT THIS POINT, BUT THE TOUCHSCREEN WILL. This is caused by the way the installer handles Kext loading but because the touchscreen is being loaded via usb and the keyboard in a different method (which I can explain in detail if you'd like, the install will be possible.
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
 
 # Messages and Facetime
 - Using Clover Configuator generate your own Serials, Board Numbers, MLB
 - There are various guides online to do this and as default they're set to essentially Null (Fakeserial)
 - This is fairly straightforward and there is lots of documentation, just don't open these apps until you've done this properly.
 
 # Finished!
 - Congratulations, there really aren't any more steps that are required. Feel free to contact me with any questions. 
