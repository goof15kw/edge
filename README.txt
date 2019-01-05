# edge
stuff that lives on the edge

This version as of 18.06 confuses LuCI and LuCI will show the interface not in the right state (only if you are looking at it. F5 will fix it).

cat > enable.sh << EOF
/sbin/uci delete wireless.@wifi-iface[1].disabled
/sbin/uci commit
wifi
EOF
chmod +x enable.sh 

cat  > disable.sh  << EOF
/sbin/uci set wireless.@wifi-iface[1].disabled=1
/sbin/uci commit
wifi
EOF

chmod +x disable.sh 

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

