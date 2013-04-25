---
layout: post
title: "Fixing a Kindle Fire Stuck in Bootloop"
date: 2013-04-24 20:13
comments: true
categories: 
- Kindle
- Hardware
---

Basically boot looping is when you see the "Kindle Fire" logo over and over again when 
you power on the device and it doesn't do anything else.

I have no idea what happens to the Kindle Fire to get it into this state but my sister 
managed to do it and this is how I fixed it. This will replace the bootloader on the device
and reset it to factory settings. Everything that you have stored on the device will be gone
and you will have to reconfigure the device. Basically as if you had just received your kindle for
the first time. Once you enter your account information it will sync with your Amazon account and you
can redownload anything that you had in your cloud storage and your books will sync with the device.
So not everything is lost but it is an inconvenience.

The nice part about this approach is if something like this happens again you should be able to fix
it on the device without having to attach it to a computer.

This is just a stock first generation Kindle Fire and the software mentioned in this post
only works on the first generation and will cause problems if used on other generations.

The first thing you are going to need is the Kindle Fire Utility which can be found here:
[Kindle Fire Utility](http://forum.xda-developers.com/showthread.php?t=2192818)

My screenshots are using version 9.6 and the link I provided at the time of posting 
is for version 9.9 but the menu choices are basically the same.
The older thread with version 9.6 is here: [Kindle Fire Utility unmanged thread](http://forum.xda-developers.com/showthread.php?t=1399889)

Install the drivers for the kindle by running the drivers.bat file that is found in the
Kindle Fire Utility download and plug in the kindle fire into your computer.

Once your device is recognized by your computer start the Kindle Fire Utility by running the run.bat
file and you should see the following

{% img /images/KindleFire/KFUHome.png %}

If your boot status isn't 4000 that fine we are about to change it into fastboot(4002) anyway to 
install some additional software. You do have to have an ADB Status of "Online" though.

Hit 1 and press enter to choose the Bootmode Menu and you should be looking at 

{% img /images/KindleFire/KFUBoot.png %}

Hit 2 and enter and your device should reboot in a few seconds and stay on the "Kindle Fire" logo.

You can keep hitting 0 and enter to recheck the ADB/Bootstatus of the device and once it is rebooted you
should see this with the Boot Status of 4002. The boot status is remembered on the device and won't allow you
to boot normally until you change this setting back to Normal(4000). No amount of rebooting the device will fix this
and is a common problem with people.

{% img /images/KindleFire/KFUFastBoot.png %}

Don't press any number and just hit enter to return to the home screen

{% img /images/KindleFire/KFUHome.png %}

From this main menu hit 3 and enter to install TWRP which is a recovery software that will need later
More information on what it is/does can be found here [TeamWin](http://www.teamw.in/project/twrp2)

After that finishes installing get back to the main menu again and hit 5 and enter to install the 
FireFireFire bootloader.

If those two things installed successfully you can go back into the Bootmode Menu and change it back 
to Normal(4000) at this point. Follow the same steps we did above to change it into FastBoot(4002).

You can disconnect your device from the computer and reboot it.
The first screen that you should see when it reboots is this one

{% img /images/KindleFire/FireFireFireMain.jpg %}

My images are a little fuzzy but the bottom of the screen says "Press power button for boot menu"
If you tap the power button (possibly a couple times if it doesn't recognize it right away)
You should see it turn into the menu below.

{% img /images/KindleFire/FireFireFireMenu.jpg %}
Which says:
Normal Boot
Recovery
Reset Boot Mode

Keep tapping the power button until it selects the Recovery option as in the picture. Once it is selected
stop and in a few seconds it will start booting up TWRP which we installed earlier. It will say "Booting..."
at the bottom of the screen for a few seconds and then should show this image for a second or so

{% img /images/KindleFire/TeamWinLogo.jpg %}

and then it will slide out of the way showing you the TWRP Menu.

{% img /images/KindleFire/TWRPMenu.jpg %}

Press on the "Wipe" button and you will see this screen.

{% img /images/KindleFire/KFWipe.jpg %}

Press on "Factory Reset" button and this screen will show.

{% img /images/KindleFire/TWRPReset.jpg %}

Just swipe to reset the device to Factory Defaults.

Then click on the House shaped icon in the top right to return to the main menu.
Click on the "Reboot" button

{% img /images/KindleFire/TWRPReboot.jpg %}

Click on "System" and the device will reboot and you will see this screen again.

{% img /images/KindleFire/FireFireFireMenu.jpg %}

Hit the power button a few times and choose "Normal Boot" instead of "Recovery" as we did before
and after a bit of time you should be presented with the screens for setting up your kindle.

That's it and if it ever happens again the software to fix the problem is already on the device
and you can reset it if happens again. Depending on exactly what happened to your Kindle Fire you
be able to get away with just clearing the cache but the factory reset should pretty much
always do the trick even if it is annoying to have to reconfigure the device and pull your apps
back down from the cloud.





