# Bluetooth
```bash
hcitool scan  # to get the MAC address of your device
bluetoothctl
agent on
scan on  # wait for your device's address to show up here
scan off
trust MAC_ADDRESS
pair MAC_ADDRRESS
connect MAC_ADDRESS
```
