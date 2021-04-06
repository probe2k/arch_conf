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
>
> xorg-iceauth (ICE block on nautilus)
>
> upower (-Rdd for dep override - tracker-miner-fs)
>
> acpi (skepticism on sensor data overrides - calibration due)

## intel-undervolt msr bug

> kernel: msr: Write to unrecognized MSR 0x150 by intel-undervolt

## package hold

> libpulse|pulseaudio|pulseaudio-bluetooth : breaks sync and media cap
>
> picom : scrot artifacts. source patch to trim 1px offset on left/right failed

## package add

*vulkan-intel -> AVD runtime error spawn*

 > emulator: ERROR: VkCommonOperations.cpp:541: Failed to create Vulkan
 >
 > cannot add library /home/probe/Android/Sdk/emulator/qemu/linux-x86_6
added library /home/probe/Android/Sdk/emulator/lib64/vulkan/libvulka
cannot add library /home/probe/Android/Sdk/emulator/lib64/vulkan/lib

#### fix

*ln -sf from ~/Android/Sdk/emulator/lib64 to ~/Android/Sdk/emulator/qemu/linux-x86_64/*

#### deps failure

> vulkan-intel
>
> vulkan-mesa-layers

#### switch from nautilus to thunar

*Package count : 572*

*Switched from chromium to brave and added pulseaudio-equalizer-gtk*
*Updated package count : 569*

*Dependencies :*

> thunar-archive-plugin
> 
> xarchiver
> 
> unzip

## [i3-gaps] urxvt-segfault on exit

-> fix

> export PERL_DESTRUCT_LEVEL=2

* Should be added in /etc/profile.d/<base.sh>
* Temp fix - added to /etc/profile.d/locale.sh

## [android-studio] device properties insufficient permission

> Error 1 retrieving device properties for ro.product.cpu.abi:
> adb: insufficient permissions for device
> See [http://developer.android.com/tools/device.html] for more information

-> fix

Kill existing adb server

> sudo ${HOME}/Android/Sdk/platform-tools/adb start-server

## [android-studio] vulkan instance error

* emulator: ERROR: VkCommonOperations.cpp:537: Failed to create Vulkan instance.

-> fix 

*pacman -S vulkan-intel*

* MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

-> fix

> sudo sysctl dev.i915.perf_stream_paranoid=0*

*Ref the same inside /etc/sysctl.d/40-dirty.conf*

> sudo echo "dev.i915.perf_stream_paranoid=0" >> /etc/sysctl.d/40-dirty.conf

* Fontconfig warning: "/usr/share/fontconfig/conf.avail/05-reset-dirs-sample.conf", line 6: unknown element "reset-dirs"

-> fix

*Eliminate <reset-dirs /> from /usr/share/fontconfig/conf.avail/05-reset-dirs-sample.conf*

* ! Cannot find Chrome. Try setting CHROME_EXECUTABLE to a Chrome executable.

-> fix

> export CHROME_EXECUTABLE=brave

* Should be added in /etc/profile.d/<base.sh>
* Temp fix - added to /etc/profile.d/locale.sh
