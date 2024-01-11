# 300 - Building Our Application

## 100 - Discover the TP-Link Smart Device

With ```python-kasa``` installed, try the following:

- Plug one of your TP-Link smart devices (here: TP-Link Smart Plug Type HS110) into the power socket.
- Press the 'discoverable' button on the smart device; a light will flash indicating that the device is advertising itself on your local wifi-network (here: TP-LINK_Smart Plug_4F10).
- Switch your wifi-network connection of your computer to the advertised network of the smart device (here: TP-LINK_Smart Plug_4F10).
- On the terminal, run the following command: ```$ kasa discover```.
- You will be prompted, if successfull, with something like the following:

```
Discovering devices on 255.255.255.255 for 3 seconds
== Outdoor Christmas Lights - HS110(EU) ==
  Host: 192.168.0.1
  Port: 9999
  Device state: True
  == Generic information ==
  Time: 2000-01-02 02:09:00 (tz: {'index': 41, 'err_code': 0}
  Hardware: 2.0
  Software: 1.5.6 Build 191125 Rel.083657
  MAC (rssi): oC:80:63:DD:4F:10 (33)
  Location: {'latitude': 51.3568, 'longitude': 5.305}
  == Device specific information ==
  LED state: True
  On since: 2024-01-09 16:54:05
  == Current State ==
  <EmeterStatus power=4.391 voltage=228.812 current=0.047 total=0.001>
  == Modules ==
  + <Module Schedule (schedule) for 192.168.0.1>
  + <Module Usage (schedule) for 192.168.0.1>
  + <Module Antiteft (anti_theft) for 192.168.0.1>
  + <Module Time (time) for 192.168.0.1>
  + <Module Cloud (cnCloud) for 192.168.0.1>
  + <Module Emeter (emeter) for 192.168.0.1>
Found 1 devices
```

## 200 - Provision the TP-Link Smart Device (Mandatory!)

You can provision (i.e. make it connect to the same wifi-network as your Home Assistant instance) your device without any extra apps by using the ```$ kasa wifi``` command:

If the device is unprovisioned, connect to its open network (here: TP-LINK_Smart Plug_4F10).

Use ```kasa discover``` (or check the routes) to locate the IP address of the device (likely 192.168.0.1, if unprovisioned)

Scan for available networks using ```$ kasa --host 192.168.0.1 wifi scan```. See which networks are visible to the device.

```
No --type defined, discovering..
Scanning for wifi networks, wait a second..
...
```

Join/change the network using ```$ kasa --host 192.168.0.1 wifi join <network to join>```. Here use the same wifi-network as the one your Home Assistant instance is connected to (here: TP-Link_1476, which is the TP-Link Router). **WARNING**: TP-Link Smart Device is not (yet) compatible with 5G wifi-network, hence choose your 2.4G equivalent channel of your router (so **not** TP-Link_1476_5G).

```
No --type defined, discovering..
Password: *****
```

Above, enter the password of the network to be joined (here: TP-Link_1476, which is the TP-Link Router). Hit ENTER.

**NOTE**: Once the TP-Link Smart Device is provisioned to the wifi-network TP-Link_1476 as the Router supports both 2.4G and 5G, we as the computer user can still connect to the 5G channel (TP_Link_1476_5G) - to benefit from a higher speed connection -  to communicate with the TP-Link Smart Device as they will then both be connected to the same router (with the same password).

## 300 - Integrate the TP-Link Smart Device in Home Assistant

See also https://home-assistant.io/integrations/tplink/

MORE ..


