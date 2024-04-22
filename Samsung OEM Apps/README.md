Samsung Core OEM Apps - Pulled by Denis Nedry! Thx! 

You can either download the few I could get uploaded to GitHub due to size, use Winget or simply use the URLs I provide to get the apps.

--Links and Info on Samsung OEM apps on the Microsoft Store--

Samsung has a publisher ID of "Samsung Electronics Co. Ltd." on the Microsoft Store, if you run into one that you can't find, *open an issue* and I will either upload the appx/msix or find the link to it.

Most Samsung Apps are visible if we search their publisher ID link via the Microsoft Store,like so:
https://apps.microsoft.com/search/publisher?name=Samsung+Electronics+Co.+Ltd.

**(Hidden from MS Store)** *indicates that this app does not seem to appear in the Microsoft Store when searching for "Samsung" apps, if you notice one I missed, please let me know with an issue.*

**---- Core Apps ----**

Samsung Settings App **(Hidden from MS Store)** - Product ID # 9P2TBWSHK6HJ
https://apps.microsoft.com/detail/9P2TBWSHK6HJ

Samsung Continuity Service **(Hidden from MS Store)** - Product ID # 9NGW9K44GQ5F
https://apps.microsoft.com/detail/9NGW9K44GQ5F

Samsung Update App - Product ID # 9NQ3HDB99VBF
https://apps.microsoft.com/detail/9NQ3HDB99VBF

Samsung Account App - Product ID # 9P98T77876KZ
https://apps.microsoft.com/detail/9P98T77876KZ

Samsung Cloud Assistant App - Product ID # 9NFWHCHM52HQ
https://apps.microsoft.com/detail/9NFWHCHM52HQ

Samsung Cloud Bluetooth Sync App - Product ID # 9NJNNJTTFL45
https://apps.microsoft.com/detail/9NJNNJTTFL45

Samsung Gallery App - Product ID # 9NBLGGH4N9R9 
https://apps.microsoft.com/detail/9NBLGGH4N9R9
(Note - Has a hidden photo editor that works only on Samsung devices, tried to RE it but is written in native code and that's not my best)

Samsung Studio App - Product ID # 9P312B4TZFFH 
https://apps.microsoft.com/detail/9P312B4TZFFH
(Note - I have patched a version of this app as a PoC, there is a set of instructions at the beginning of this apps code that tell it to check the system and deny if not Samsung hardware, I nop'ed those out so the app *just works* - See my other repo.)
