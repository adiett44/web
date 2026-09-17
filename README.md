sudo modprobe -r nvme 2>/dev/null
sudo modprobe nvme default_ps_max_latency_us=0 admin_timeout=120
sudo setpci -s 00:1d.0 BRIDGE_CONTROL=0x40:0x40
sleep 0.5
sudo setpci -s 00:1d.0 BRIDGE_CONTROL=0x00:0x40
sleep 1
echo 1 | sudo tee /sys/bus/pci/rescan
sleep 2
echo "0000:06:00.0" | sudo tee /sys/bus/pci/drivers/nvme/bind 2>/dev/null
sleep 3
echo "--- DMESG LOG ---"
dmesg | grep -i nvme | tail -n 12
echo "--- DISK LIST ---"
lsblk



