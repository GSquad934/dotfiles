# DWM Status Bar
By default, DWM has a very plain bar with almost no information in it. The status bar can be customized with one/several BASH script(s). Here is what mine looks like:

![](https://hostr.co/file/jHQRjOaMMQ9t/dwm-statusbar.png)

* 📦 0 : indicates how many updates are available (script: *dwmupdates*)
* 🖥 24% ▃ : indicates the CPU usage. The bar will fill-up if the CPU is used more (script: *dwmcpu*)
* 🧠 0.61GB/1.93GB : indicates the RAM usage (script: *dwmmemory*)
* ⬇  7.9MB ⬆  48KB : indicates the download/upload network traffic usage (script: *dwmnet*)
* 💾 5.0G (18%) : indicates the disk space usage where "/" is mounted. Other disks can be added by modifying the script (script: *dwmdisk*)
* 🌡 0 : indicates the CPU temperature. (script: *dwmtemp*)
* 🔊 100% : indicates the volume level. The icon will change depending on the volume level (script: *dwmvol*)
* 🕒 Mon, February 22 14:31 : indicates the current day, date and time in 24H format (script: *dwmclock*)

These scripts must be in your *$PATH* for the status bar to work. The script called *dwmbar* is the one launching the status bar (add it to your *.xinitrc*) while all the other ones are used to retrieve the different information.

This bar integrates niceley with [my build of DWM](https://github.com/GSquad934/dwm).

# Contact
You can always reach out to me:

* [Twitter](https://twitter.com/gaetanict)
* [Email](mailto:gaetan@ictpourtous.com)
