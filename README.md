# domoticz-homematicip-workbook
Guide on how to integrate eQ-3 Homematic CCU3 with selected Homematic IP Devices into Domoticz Home Automation System. 
This guide has been developed for personal use only.

### Purpose
To integrate the [HomeMatic](https://www.homematic.com) Smart Home [Central Control Unit (HmIP-CCU3)](https://www.eq-3.com/products/homematic/detail/smart-home-central-control-unit-ccu3.html) in [Domoticz](https://www.domoticz.com/) Home Automation System.
This document has been developed for personal use only - as a supplemental reference - use at your own risk.
It is an addendum to the [Domoticz Homeautomation Workbook](https://github.com/rwbl/domoticz-homeautomation-workbook).

### Overview
Described are various ways on how to integrate Homematic IP devices (connected to the CCU) in Domoticz.
Homematic offers a variety of devices. This document covers the ones used by the author.
Whilst evolving, new devices will be added step-by-step or solutions reworked - and captured in this document.
The examples are based on good-practise by the author. It does not mean that there are other and probably better ways.

There are two key chapters:
* **Functions** - describing dedicated solutions with Homematic IP devices
* **Explore** - looking into ways of using API's & communication between the CCU and Domoticz

Functions with Homematic IP devices:

* Alert Indicator (HmIP-MOD-OC8, Receiver and switching module with 8 open-collector switching outputs, kit)
* Battery Check (All HmIP-Devices)
* Coffee Machine Monitor (HmIP-PSM, Pluggable Switch and Meter)
* E-Paper Status Display (HmIP-WRCD, Wall-mount Remote Control with status display, kit)
* Garage Door Monitor (HmIP-SWDM, Window / Door Contact - magnet)
* Heating Unit Gas Usage (HmIP-FCI1, Contact Interface flush-mount, 1 channel )
* Heating Unit Temperature (HmIP-STE2-PCB, 2-channel-Temperature Sensor )
* HM-RC-19 = CUx Daemon (CUx-D), interface between CCU-Logic (ReGa HSS) and external (incl. virtual) devices
* Duty-Cycle Monitor (HmIP-CCU3 Device Object)
* Pluggable Switch and Meter (HmIP-PSM, Pluggable Switch and Meter)
* Postbox Notifier (HmIP-SWDO, Window / Door Contact optical)
* Radiator Thermostats (HmIP-eTRV-B/eTRV-2)
* Remote Control (HmIP-RC8, Remote Control with 8 buttons)

### Domoticz
* The devices to control Homematic devices are mainly virtual devices (Hardware type "Dummy").
* The Automation Events are developed in [dzVents](https://www.domoticz.com/wiki/DzVents:_next_generation_Lua_scripting) - Domoticz next generation Lua scripting.
* The [Plugins](https://www.domoticz.com/wiki/Developing_a_Python_plugin) in [Python 3](https://www.python.org/).
* The communication between Domoticz and the CCU v.v. is handled via HTTP XML- or REST-API requests with the CCU Addons XML-API, CCU-Jack and CUx-Daemon, but also explored the Homematic JSON-API and XML-RPC-API.

### Other
* [Node-RED](https://nodered.org/) used for tests and some tools.

### Credits
A **BIG THANK YOU**, to the developers of Domoticz, Homematic, RaspberryMatic, Homematic addons, Tools and to all sharing information about Domoticz and/or Homematic.
Without these, it would not be possible to build this project and write this document.

### Licence
GNU GENERAL PUBLIC LICENSE v3.0.
