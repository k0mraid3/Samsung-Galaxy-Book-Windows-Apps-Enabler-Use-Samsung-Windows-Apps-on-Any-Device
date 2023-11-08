# Samsung-Galaxy-Book-Spoofer-for-Windows-11
Windows 10 &amp; 11 Samsung Galaxy Book Spoofer -- Tool for making *Some* Samsung apps work on any Windows 10 or 11 PC

This BAT will make Apps like Samsung Notes, Samsung Live Wallpaper, Galaxy Book Settings & Samsung Gallery function on non-galaxy Book devices. It works for some samsung Apps, but doesnt work for others, such as Samsung Studio Plus or Bixby, It is likely that i am missing one of the reg keys for it.  

It will set a series of Reg values, copy itself into start (GoaL was to make it re-set these props at boot, if you dont want this, remove line 14. This is what line 14 looks like. --> ```copy "Galaxy_Book3_Pro_Spoofer.bat" "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp" /Y)```

I have not had any kind of issues occure from using this script but i am using it on a PC i Built myself, so the values that this script changes where still set to default OEM values on my system. Regardless, use at your own risk. 

--Break-down--

The first part of the script sets the following registry values:

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

The second part of the script copies itself, "Galaxy_Book3_Pro_Spoofer.bat", to the Startup folder. This file SHOULD be executed every time the computer starts up. As mentioned above, if you dont want this, simply remove this bit. 

The final line of the script exits the batch script.



Enjoy, let me know if you guys figure out how to get the other apps working. 
