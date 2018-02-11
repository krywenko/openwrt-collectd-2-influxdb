# openwrt-collectd-2-influxdb

it will use the CollectD software for network and hardware info, if using it for your IOT archival data you just need to configure to output a CSV data base every once in a while to update to influxdb via the software
its default send is every 30 seconds but that is adjustable up to 4 hours or more .

just edit influxsend to adjust timing setting
to tell the software where your csv are located edit cp-csv
and to edit influxdb setting edit settings in Sendinflux.pl

In the openwrt platform all the high write data is stored in memory so at reboot all data is lost so if you are worried about that leave the setting for timer at 30sec all you need to do once you copy it to your Openwrt / dir is set up a small bash script to run at boot that first copies the runfiles folder to the /tmp then execute influxsend afterward . 
