# CPUInfo Screen Dashboard Configuration for Raspberry Pi

This repo contains a config script that prints basic system information on a cheap GPIO-driven screen. The dashboard is optimized for Tor node monitoring, but can be used for any other purpose where you want to see the amount of network traffic.

| Display row | Metric                   |
|-------------|--------------------------|
| 1           | Uptime                   |
| 2           | CPU load and temperature |
| 3           | RAM utilization          |
| 4           | Disk utilization         |
| 5           | Network traffic received |
| 6           | Network traffic sent     |


### Setup
**Screen:** 84x48 Nokia 5110 LCD with a pcd8544 controller, sold as [RPi 1.6" CPUInfo Screen](https://www.ebay.com/sch/i.html?_nkw=Raspberry+Pi+1.6%22+CPU+Info+Screen) for around $10

**Driver:** This config script is utilizing C program from [this repository](https://github.com/MichelVos/rpi_cpu_infoscreen) that drives the display


### Installation
1. Compile the `test_bcm8544` from the linked repository
2. Rename `test_bcm8544` to `display`
3. Create a cronjob that runs `status.sh` every minute
```
pi@torpi:~ $ crontab -e
* * * * * /home/pi/status.sh
```

![Final product](https://github.com/jankais3r/rpi-cpuinfo-screen/raw/master/demo.jpg)
