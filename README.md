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
