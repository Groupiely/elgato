99;6u
 Put file into your .config directory (if it does not work perfect you can also copy them to /etc)
 Folders are already constructed as is so just merge should do the trick

 PS :" i still had some issue with GNOME and KDE with this, i think they use their own Audio tool on top of wireplumber/pipewire"

A solution that i don't have in hand is to create a udev rule, i did the base of the file but you need to replace VendorID and ProductID
with the one for your microphone

lsusb
find your elgato
lsusb -d 0fd9:006e --verbose

That way you will have all the info about your wavelink, the vendorID should be the same but productID should change

the udev rule needs to be in /etc/udev/rules.d

After you need to do sudo limine-update to make the kernel take the udev into account.


PS : Now i dont need the udev rule anymore but i did need it on KDE/GNOME
