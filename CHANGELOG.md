# ChangeLog domoticz-homematicip-workbook

## 20231031
* UPD: XML-API addon - New security access token as from XML-API v2.2

## 20230605
* NEW: Function Custom  Pages - Various jQuery DataTables embedded in Domoticz custom pages, like device statelist, devicelist, statelist, roomlist.
* NEW: Function Pluggable Switch and Meter (HmIP-PSM) - PSM Switch, PSM Power & Energy, PSM Power Monitor.
* NEW: Function Statelist Node-RED - Reworked using Node-RED v3.0.2, node-red-dashboard (3.0.2), node-red-node-ui-list (0.3.6).
* NEW: Appendix Reference Automation Script XML Parsing - Examples parsing XML tree structures from HTTP responses like CCU Addon XML-API, Homematic Remote Script API.
* NEW: GitHub folder src with Homematic scripts, Domoticz automation scripts dzVents, Custom pages.
* UPD: Function E-Paper_Status_Display-hmip-wrcd - Domoticz automation script added new pages for Gas & Power Usage; Removed Covid page; Updated Domoticz Selector Switch.
* UPD: Function Thermostat State Custom Page (HmIP-eTRV) - Reworked the page, uses the jQuery DataTables plug-in instead HTML table, column conditions for Level & Voltage.
* UPD: Reworked all chapters & scripts.
* DEL: Function Battery Check - Removed solutions not used: CCU-Jack, Remote Homematic Script, Push On Button.
* DEL: Function Coffee Machine Monitor - Removed as not used anymore. Use PSM Power Monitor instead.
* DEL: Function Duty Cycle Monitor - Removed solution not used: System Command.

## 20230211
* NEW: Function Battery Check - Remote Homematic Script solutions Timer (explored) / Push On Button (explored) / Selector Switch (in use) embedded in dzVents script.
* NEW: Function Radiator Thermostats (HmIP-eTRV) - Domoticz Automation Event dzVents to get thermostat attributes and to set setpoints using embedded Homematic Scripts which are submitted to the CCU.
* UPD: Explore XML-RPC API - Renamed to Explore Remote Homematic Script API.
* UPD: Explore Remote Homematic Script API - Reworked the chapter; Added Domoticz, Node-RED & Python examples.
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
