# 300 - Building Our Application

With ```python-kasa``` installed, try the following:

- Plug one of your TP-Link smart devices (here: TP-Link Smart Plug Type HS110) into the power socket.
- Press the 'discoverable' button on the smart device; a light will flash indicating that the device is advertising itself on your local wifi-network (here: XXX).
- Switch your wifi-network connection of your computer to the advertised network of the smart device (here: XXX).
- On the terminal, run the following command: ```kasa discover```.
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
  + <Module Cloud (cloud) for 192.168.0.1>
  + <Module Emeter (emeter) for 192.168.0.1>
Found 1 devices
```

More ...
