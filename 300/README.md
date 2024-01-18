# 300 - Building Our Application

**TIP**: Use [Fing](https://github.com/vanHeemstraSystems/fing) if you need to scan your home network for devices.

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

### 100 - Automatic Integration

1) Inside your Home Assistant instance, open https://home-assistant.io/integrations/tplink/
2) Click on the button: **Add Integration to my (Home Assistant)**.
3) When asked to open page in your Home Assistant, edit the URL so it becomes ```http://127.0.0.1:8123```. Click **Open link**.
4) Follow the instructions.

### 200 - Manual Integration

1) Inside your Home Assistant instance go to Settings > Devices & Services. Choose the tab **Integrations** and if the ```TP-Link``` integration is not already there, click the button **+ ADD INTEGRATION**.
2) Search for ```TP-Link``` to set up a new integration.
3) When listed, click on the found ```TP-Link``` list item.
4) When asked what do you want to add, choose ```TP-Link Kasa Smart```.
5A) We can use the Hostname or IP address of our TP-Link device, but as we have already provisioned it to the same wifi-network as the one Home Assistant is connected to, we leave the field empty so discovery will be used instead. Click **SUBMIT**.
5B) Alternatively, we can use the Hostname of our TP-Link device, which we can retrieve when opening the iOS TP-Link Kasa app on our mobile device and look up the Device Info:

![14AFA3A4-0D8E-4F94-9FCD-CC5130A75224](https://github.com/vanHeemstraSystems/home-assistant-tp-link-kasa-smart/assets/1499433/9d489f52-ba8b-488c-a8bf-e19ed95991f3)

iOS TP-Link Kasa App, Device Info

We'll then find the Network Info (here: ```TP-Link_1476```), which is the WiFi Network this TP-Link Smart Plug device was provisioned to.

Next, open the web interface of this TP-Link Router, by going to ```[http://tplinkwifi.net/](http://tplinkwifi.net/)``` or ```[http://192.168.0.1](http://192.168.0.1)``` alternatively from a browser that is connected to the same Network (here: ```TP-Link_1476```). 

**NOTE**: If this is your first time logging into to the web interface of your TP-Link Router, you will be asked to create an administrator password. Choose something memorizable, and login.




MORE ..


