# spdMerlin-Hook
Small program to put a hook call in @JackYaz spdMerlin script that will call an external shell script (non-blocking) passing the download and upload speeds of the recent run.

This somewhat mimics Asuswrt-Merlin various service and event hooks - service-start, service-end, etc.

When executed (tested on the last few releases of spdMerlin) it checks for and creates if necessary an executable script in /jffs/scripts called spdmerlinhook.

It then makes a backup of spdMerlin (spdmerlin.orig), then puts a few lines rigth at the end of a speedtest run. It calls spdmerlinhook as a background task - so it doesn't block spdMerlin from completing and exiting.

I use this hook to watch download speeds from my T-Mobile Sagemcom Modem/Gateway. If the speed drops below a setpoint, I reboot the Sagemcom Fast modem. I have found in 95% of the cases, this gets my speeds back to 100+ Mbits/sec.
BTW, I have the script that reboots the Sagemcom in another repository of mine - tmo.sh

