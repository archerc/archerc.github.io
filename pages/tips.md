---
layout: page
title: 
---

- symbolic link in windows without adminstrator

```
mklink /J [link] [target]
```

# Understanding How Windows Key Re-Mapping Works
Windows doesn’t have a default setting to allow for disabling the key, so what we have to do is re-map the key to something non-existent so as to completely disable it. To do this manually, you’d open up regedit.exe and browse down to the following key:

> HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout

[!image](http://www.howtogeek.com/wp-content/uploads/2007/08/ximage27.png.pagespeed.gp+jp+jw+pj+js+rj+rp+rw+ri+cp+md.ic.rlUvA90AVL.png)

Here’s the format of the binary data in the Scancode Map key, with the important parts in bold and various colors:

> 00000000 00000000 02000000 00003A00 00000000

Here’s how it works:

- The first 16 zeros are just there to waste space.
- The “02” in bold represents how many keys you are going to re-map plus 1. (It really represents the length of the data, but whatever)
- The orange bolded “0000” is the key we actually want Windows to map TO, which in this case is nothing, or 0.
- The blue bolded “3A00” is the key we are mapping from, in this case the caps lock key.
- The next 8 zeros are there to waste space as the null terminator.

You can map between multiple keys by incrementing the “02” and then adding another of the colorful bold blocks in the middle. The 3A00 in the mix is the scan [code](https://msdn.microsoft.com/en-us/library/aa299374(v=vs.60).aspx).  For example, if you wanted to disable the caps lock key and then change scroll lock into a caps lock key:

> 00000000 00000000 03000000 00003A00 3A004600 00000000

It might seem complicated, but it’s really fairly simple once you start working with it.

# Downloadable Registry Hack to Disable or Remap the Caps Lock Key
Now that you’ve learned how these things work internally, you can download and extract the zipfile which contains the following files:

ChangeCapsToControl.reg	Changes Caps Lock to be a Control key
ChangeCapsToShift.reg	Changes Caps Lock to be a Shift key
SwitchCapsToScrollLock.reg	Disables Caps Lock and swaps Scroll lock to be Caps Lock
KillCapsLock.reg	Disables Caps Lock
DisableKeyboardRemap	Uninstalls the preference by deleting the key
Once you’ve applied one of these registry files, you’ll have to reboot your computer for it to work. To uninstall, you can use the uninstall registry tweak, or you can simply delete the Scancode Map key entirely.

[Download Keyboard Mappings Registry Tweaks](http://www.howtogeek.com/wp-content/uploads/gg/KeyboardMappings.zip)

