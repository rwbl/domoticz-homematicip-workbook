# ChangeLog domoticz-homematicip-workbook

## 20230207
* NEW: Function Radiator Thermostats (HmIP-eTRV) - Domoticz Automation Event dzVents to get thermostat attributes and to set setpoints using embedded Homematic Scripts which are submitted to the CCU.
* NEW: Explore Remote Homematic Script API - Added Domoticz, Node-RED & Python examples.
* UPD: Explore XML-RPC API - Renamed to Explore Remote Homematic Script API; Reworked the chapter.
* UPD: Polished up several chapters.

## 20230122
* NEW: Function Heating Unit Gas Usage (HmIP-FCI1) - Measure the gas meter counter.
* NEW: Function Heating Unit Temperature (HmIP-STE2-PCB) - Measure heating flow and return temperatures.
* NEW: Tool Thermostat State Custom Page - View all Thermostats at a glance (Setpoint SP, Process Value PV, Diff SP-PV, Level, Battery voltage).
* UPD: RaspberryMatic CCU replaced by the Homematic Smart Home Central Control Unit [CCU3](https://www.homematic-ip.com/en/products/detail/smart-home-central-control-unit-ccu3.html).
* UPD: Function Battery Status - Renamed to Battery Check; Domoticz & Homematic Scripts reworked incl. Homematic Addon CCU-Jack REST-API.
* UPD: Function Garage Door Monitor - Reworked Homematic script & Domoticz event.
* UPD: Function Homematic Duty-Cycle Monitor - Replaced system variable solution by the new Homematic Device HmIP-CCU3; Corrected the recurring event "all day every 5 minutes".
* UPD: Function Remote-Control - RaspberryMatic to Homematic, Homematic script simplified.
* UPD: For some functions replaced the XML-API CCU Addon by [CCU-Jack Add-On](https://github.com/mdzio/ccu-jack) REST-API for getting or settings Homematic values (uses JSON instead XML).
* UPD: Minor changes.

## 20210613
* NEW: Published first version [Domoticz Forum](https://www.domoticz.com/forum/viewtopic.php?p=276229#p276229).

## 20210218
* NEW: Started with some first ideas.
