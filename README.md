# edge
stuff that lives on the edge


root@cadillac:~# cat enable.sh 
#/sbin/uci set wireless.@wifi-iface[2].disabled=1
/sbin/uci delete wireless.@wifi-iface[2].disabled
wifi

root@cadillac:~# cat disable.sh 
/sbin/uci set wireless.@wifi-iface[2].disabled=1
#/sbin/uci delete wireless.@wifi-iface[2].disabled
wifi


crontab: 
0	17	*	*	*	/root/enable.sh
30	18	*	*	*	/root/disable.sh
30	19	*	*	*	/root/enable.sh
33	21	*	*	*	/root/disable.sh
#v4 17h-18h30 20h-21h30 02 mai 17
#v3 19h-21h35 29-08-16
#V2 on-off-on-off 5-06-16
#V1 update a 33 le 18-04-16

Needs timezone set
need to run:
/etc/init.d/cron enable  
/etc/init.d/cron start 

