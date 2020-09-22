## glibc v2.31-5 stat 

> [   69.585062] urxvt[1229]: segfault at 110 ip 00007f79bb4d9c6d sp 00007ffe99b49f20 error 4 in libc-2.31.so[7f79bb4c1000+14c000]

### fix ->

*downgrade glibc to v2.31-2*


## dmesg | grep error

> [   10.197956] ACPI Error: Aborting method \_SB.PCI0.B0D4.PPCC due to previous error (AE_AML_INTERNAL) (20200528/psparse-529)

## regulatory db fix 

*install and setup crda and wireless-regdb(dependency)*

## package removal (xorg-apps)

> xorg-luit (Terminal export override substitute working)
> xorg-iceauth (ICE block on nautilus)
