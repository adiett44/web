sudo setpci -s 00:1d.0 BRIDGE_CONTROL=0x40:0x40 && sleep 0.2 && sudo setpci -s 00:1d.0 BRIDGE_CONTROL=0x00:0x40


echo 1 | sudo tee /sys/bus/pci/rescan

dmesg | grep -i nvme | tail -n 10


lsblk



