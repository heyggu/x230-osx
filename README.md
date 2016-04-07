## USB problems:
There are many USB patches, EHCI, UHCI, ICH9 USB sleep, EHCI sleep/ownership, some are generic, some are organized by chipset.
If you have problems with USB ports, if you see errors or warnings in kernel log about EHCI or UHCI, you can try these patches. 

## Sleep problems:
Problems with sleep are usually related to power management and USB.
If the system goes to sleep and wakes immediately, look for "Wake reason" in kernel log and edit method _PSW or remove _PRW from that device in DSDT.

## CMOS reset:
Apply the RTC patch.
If you have CMOS reset after sleep/wake/reboot, you need to patch AppleRTC.

## Audio:
You can use HDEF (or AZAL to HDEF if you already have device AZAL) and a codec patch (ALC*) if you will use a patched AppleHDA.
Make sure layout-id in DSDT (hex) coincides with LayoutID in AppleHDA (dec).

DSDT: LayoutID (dec, base 10)
AppleHDA: layout-id (hex, base 16)

(12)10 = (0xc)16
(889)10 = (0x379)16
