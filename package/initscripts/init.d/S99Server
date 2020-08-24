#!/bin/sh

echo 'load wilc-sdio module driver ...'
modprobe wilc-sdio
sleep 10

echo 'init wlan0'
ifconfig wlan0 up
sleep 10

echo 'fix wlan0 ip address'
ifconfig wlan0 192.168.0.1
sleep 10

echo 'run wilc in AP mode, SSID=iMX6-ap1, Password=12345678'
hostapd /etc/hostapd_ap.conf -B &
sleep 10

echo 'start DHCP'
/etc/init.d/S80dhcp-server start &

echo 'done'
