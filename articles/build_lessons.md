# Lessons I learnt during the build, but wish I didn't need to
Your mileage may vary - some of this will probably be very obvious to others (I hope so!)

In no particular order:
- ALL the motor directions had to be swapped in the example config file from Voron Design. That's fine, but half of the z-axis motor are opposite directions, so getting them all inverted was not obvious
- Lubricate the rails prior to installation, seriously
- Set the z-axis rails just a little more above the bottom (spec'd as 3mm) otherwise fitting the belt covers is a real pain
- Obsess over a square frame. I assembled mine once reasonably well, then carried it to my only really flat surface, the stone kitchen bench, and resquared it all, then went through and rail by rail put locktite on all the screws as I reinstalled them. It seems to have stayed square
- De-rack the XY axis - the manual mentions it, but until I found this video (XXX) on the Voron site, I was not doing it right
- A few people talk about XY belt tensions, not a lot about Z - set them all to ~110-120Hz using some phone app. When you pluck them they will all sound the same
- After a particular update to klipper (v0.10.0-546) or maybe it was the RPi (4) update it started randomly disconnecting from WiFi after about 10 minutes. Lots of ideas on how to fix it... in [this](https://community.octoprint.org/t/octopi-losing-network-connection-mid-print/16315/163) very long thread and I ended up adding this [cron job](https://gist.github.com/jacobpretorius/1c479ec38e8021196215fd2e9ae74675)
```
sudo crontab -e
*/5 * * * * /bin/ping -q -c10 192.168.8.1 > /dev/null 2>&1 || (ip link set dev wlan0 down ;ip link set dev wlan0 up ;/usr/bin/logger wifi on wlan0 restarted via crontab)
```
- to check if it is restarting the WiFi check the syslog ` tail -10 /var/log/syslog `
