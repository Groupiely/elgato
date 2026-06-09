# I'm working on a definitive solution for Elgato Wave:1 and Wave:3 :

## New V2 branch should be uploaded this week after first test

**The main repo is for now not relevant at all**

- the wireplumber conf file did help a little
- The udev is a really basic autosuspend off, not relevant i think following the
  discovery i made.
- the pipewire is more to optimize sound timing/crackling and random sound not
  working due to clock rate/timing issue, but it is not even the optimized one
  (still working on it)

> [!IMPORTANT]
> For those interested, please do not download file here, once uploaded please
> only check the version2 branch as the real work will be here :

1. UCM2 profile creation for Wave1 (will be tested on my side) and Wave 3
   (similar device but can't test it)
2. Better wireplumber workaround, (More an updated bandaid, will not work on it,
   except to make it work, but not a real fix, any issue on usb port/pipewire *
   wireplumber will cause it to stop working, reloading service is not something
   i deemed OK)
3. Udev + service for script to solve node issue on KDE/GNOME (not the most
   elegant, but should work fine, easier to do. no need to work on others
   package directory which is a plus i think)

#### Objective 1 and 3 are my real goals, the 2 is just a quick fix if it take time to make it work

My goal is to find a solution that could be sent as a commit to pipewire to be
upstream, to have our elgato working plug&play :)[^1]

Otherwise if i can make the service solution work perfectly, thinking about
working on a GUI Tools to provide same feature as Wave:Link on Linux

> Stay tuned !

[^1]: First real project so don't have any hope!

> [!WARNING]
> :warning: You can test but it's really just bad :warning:

~~# ElGato bandaid fix~~

~~## Some broken fix for those using Elgato Wave 1 or 3 for both output in
input~~

~~When i switched to Linux, i encountered an issue with my ElGato Wavelink
where~~ ~~the input (microphone) didn't work right out the box, it was detected,
but it~~ ~~seems like the microphone weren't able to wake-up once i needed it in
an app~~

~~With some intense switching in Pavucontrol, choosing only input or output,
then~~ ~~put it back in Output Stereo + Mono input, i was able to make it work
(manip~~ ~~needed to be done while app was actively searching for it)~~

~~After some research, my theory was related to a wake-up signal never coming
when~~ ~~needed, so i did tests to just make it always activated. It does not
mean audio~~ ~~is captured 100 % of the time, but that the microphone is just
waiting to be~~ ~~used.~~

~~To be perfectly honest, this script is not working fine, it did improve
things~~ ~~but it's clearly not perfect solution. moreover, now that i switched
to a WM~~ ~~(niri), the problem does not occur anymore so i didn't tried to
improve it.~~

~~Now that i had uploaded it on Github, i will try to improve it for those
also~~ ~~having those issues~~

~~## SOP~~

~~- Put file into your .config directory (if it does not work perfect you can
also~~ ~~copy them to /etc)~~ ~~ ~~- Folders are already constructed as is so
just merge should do the trick~~

~~PS :" i still had some issue with GNOME and KDE with this, i think they use~~
~~their own Audio tool on top of wireplumber/pipewire"~~

~~### Some fix i tried were not available on my side anymore since i deleted
them after quiting KDE/GNOME.~~

~~I did some really simple udev rule, i don't think it work as intended as of
now~~ ~~i need to do more research and test before i can confirm it do work, i'm
still~~ ~~providing an SOP for those who want to try or to make it work from
here.~~

~~- Open your Terminal of choice and follow these commands~~ ~~- lsusb~~ ~~-
find your elgato and note the VID/PID~~ ~~- It should be sufficient, but to be
sure and to have more info to find how to~~ ~~improve it you can look for more
info~~ ~~- lsusb -d 0fd9:006e --verbose~~ ~~- You can pipe it into a file for
better readability, or others things (make~~ ~~it a json for processing, or many
others things)~~

~~That way you will have all the info about your wavelink, the vendorID should
be~~ ~~the same but productID should change~~

~~## The udev rule needs to be in /etc/udev/rules.d~~

~~# After you added the udev file you need to update your kernel parameters to
be detected at next reboot, in my case on CachyOS with limine 'sudo
limine-update'~~

# TO BE CLEAR, THE UDEV FILE PROVIDED WAS NOT TESTED, IF YOU ARE UNSURE OF WHAT YOU DO PLEASE DO NOT USE IT, I REJECT ALL RESPONSABILITY IN CASE OF DAMAGE ON YOUR DEVICE~~`
