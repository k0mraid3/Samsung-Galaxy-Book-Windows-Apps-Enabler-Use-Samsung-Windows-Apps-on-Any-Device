# Samsung-Galaxy-Book-Spoofer-for-Windows-11
Windows 10 &amp; 11 Samsung Galaxy Book Spoofer -- Tool for making *Some* Samsung apps work on any Windows 10 or 11 PC

---- PART 1 - Bat File & REG keys.

This BAT will make Apps like Samsung Notes, Samsung Live Wallpaper, Galaxy Book Settings & Samsung Gallery function on non-galaxy Book devices. It works for some samsung Apps, but doesnt work for others, such as Samsung Studio Plus or Bixby, It is likely that i am missing one of the reg keys for it. It also seems i need to look more into the "Galaxy Book Experience" App for windows.

It will set a series of Reg values, and copy itself into Start (goal was to make it re-set these props at boot, if you don't want this, remove line 14. This is what line 14 looks like. --> ```copy "Galaxy_Book3_Pro_Spoofer.bat" "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp" /Y)```

I have not had any issues occur from using this script but I am using it on a PC I built myself, so the values that this script changes are/were still set to default OEM values on my system. Regardless, use at your own risk. 

--Break-down--

The first part of the script runs as admin and sets the following registry values:

HKLM\HARDWARE\DESCRIPTION\System\BIOS\SystemProductName: Sets the product name to "NP960XFH-XA4US".

HKLM\HARDWARE\DESCRIPTION\System\BIOS\SystemFamily: Sets the system family to "Galaxy Book3".

HKLM\HARDWARE\DESCRIPTION\System\BIOS\SystemVersion: Sets the system version to "Ultra".

HKLM\HARDWARE\DESCRIPTION\System\BIOS\SystemManufacturer: Sets the system manufacturer to "Samsung".

HKLM\HARDWARE\DESCRIPTION\System\BIOS\SystemSKU: Sets the system SKU to "6531064".

HKLM\SYSTEM\HardwareConfig\Current\SystemFamily: Sets the system family to "Galaxy Book3".

HKLM\SYSTEM\HardwareConfig\Current\SystemManufacturer: Sets the system manufacturer to "Samsung".

HKLM\SYSTEM\HardwareConfig\Current\SystemSKU: Sets the system SKU to "6531064".

HKLM\SYSTEM\HardwareConfig\Current\SystemProductName: Sets the product name to "NP960XFH-XA4US".

HKLM\SYSTEM\HardwareConfig\Current\SystemVersion: Sets the system version to "Ultra".

HKLM\SYSTEM\ControlSet001\Control\SystemInformation\SystemManufacturer: Sets the system manufacturer to "Samsung".

HKLM\SYSTEM\ControlSet001\Control\SystemInformation\SystemProductName: Sets the product name to "NP960XFH-XA4US".

The last part of the script copies itself, "Galaxy_Book3_Pro_Spoofer.bat", to the Startup folder. This file SHOULD be executed every time the computer starts up. (As mentioned above, if you don't want this, simply remove this bit.) The final line of the script exits the batch script.




------------- PART 2 -- Installing Patched "Samsung System Support Service" (To get things like Multi-control, Samsung Settings & a few others working)


1- Unzip and extract the "SamSysSupSvc" folder, to C:\ drive, so that the end path looks like this = "C:\SamSysSupSvc", It should ALREADY contain a patched version of the "SamsungSystemSupportService.exe", but just in case, I've attached a patched one to the repo, so if it ever automatically updates, all you need to do is drop the patched.exe into C:\SamSysSupSvc and rename it to remove the "-patched" line. 

<img width="773" alt="image" src="https://github.com/k0mraid3/Samsung-Galaxy-Book-Spoofer-for-Windows-10-11/assets/62849592/be1a40a9-b72b-46f5-af10-c1cae3862280">

2- Now, we need to load the drivers, so we need to open windows device manager & find -> Other Devices -> Continuity_msg_spp 
Depending on how many Samsung devices you have connected to your PC, you may see one or more "Continuity_msg_spp", we need to manually update the driver(s) to these with ones we just put in C:\SamSysSupSvc.

<img width="581" alt="image" src="https://github.com/k0mraid3/Samsung-Galaxy-Book-Spoofer-for-Windows-10-11/assets/62849592/620569f3-db2d-4691-8813-8ebb1da54836">

3- Right click "Continuity_msg_spp" and click "Update Driver", on the next pop-up, click "Let me pick from list of available drivers on my computer", on the next pop-up, click "Show all devices" and hit "Next", then we click "Have Disk" at the bottom right. Now we navigate to C:\SamSysSupSvc, it will be the only visible driver in that directory, install it for each "Continuity_msg_spp".

4- Now open a command prompt AS ADMINISTRATOR. (Hit the Windows key + X, select "Terminal (Admin)) or type "cmd" and select "Run as Administrator" 

<img width="596" alt="image" src="https://github.com/k0mraid3/Samsung-Galaxy-Book-Spoofer-for-Windows-10-11/assets/62849592/1831adf7-8e6f-4c2c-8585-623590f3760c">

Now in an administrator command prompt, run the following to create the service manually. 
``` sc create SamSysSupSvc binPath=c:\SamSysSupSvc\SamsungSystemSupportService.exe start=auto ```

If all works, it should automatically be installing Samsung apps, do a reboot and look for "Samsung Settings". Most things should now work. Check the Microsoft store if you don't find Samsung apps in recently installed, they may still be installing. 

Enjoy, let me know if you guys figure out how to get the other apps working. 
