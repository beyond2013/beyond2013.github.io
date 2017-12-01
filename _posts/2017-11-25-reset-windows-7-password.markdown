---
layout: default
title:  "How to reset windows 7 password"
comments: true
categories: windows7 password-reset 
---

Today a friend asked me to help him reset the password of one of his laptops running windows 7. I run in to this situation quite often so I thought rather than searching the web everytime i write them for future use here. 

1. I already had a windows 7 bootable but the laptop could not boot from it. So i booted using windows 10 bootable usb.
2. Booting Elite Notebook 6930p was a bit tricky as the BIOS options were spread across different pages.
3. So after enabling UEFI in setup, I could finally boot.
4. To find various drive letters/volume caption assigned to drives use following commands:
``` dos
wmic logicaldisk get name
wmic logicaldisk get volume
```
5. Followed by these commands, remember to replace the appropriate drive letter in place of x, and say Yes in repsonse to overwrite confirmation
``` dos
copy x:\windows\system32\utilman.exe x:\ 
copy x:\windows\system32\cmd.exe x:\windows\system32\utilman.exe
```
6. Restart the system this time booting from the windows 7, and press the accessibility button on the bottom left corner, which sould open the command prompt
7. Type the following commands to reset password (replace username with the existing username and newpassword with the new password)
``` dos
net user username newpassword
```
8. close command prompt and login using new password
9. to reverse the effect of step 5 boot again using bootable usb and type the following in recovery command prompt and confirm overwrite by Yes
``` dos
copy x:\utilman.exe x:\windows\system32\utilman.exe
```
