# domoticz-homematicip-workbook - TODO.md
Actions to complete till next version of the book.
Any ideas to be captured in IDEAS.md.

## NEW: Heating Unit Flow Temperature Threshold
Set a low threshold for the T1 “Vorlauf” temperature to check if the Heating Unit is working.
Sent a notification in case T1 below threshold.
This can be done in the Automation Event.
```
-- Idx user var defining the temperature low threshold
local IDX_TH_HEATING_FLOW_TEMPERATURE = 31

-- Notification flag to ensure the notification is only sent once till the temperature is above threshold again
data = { notified = { initial = 0 } },
	
-- Get the temperature threshold from user var to check if heating unit is running ok
local temperaturethreshold = domoticz.variables(IDX_TH_HEATING_FLOW_TEMPERATURE).value
-- Log the measured, and threshold temperature
domoticz.log(("Temperature:%.0f, Threshold:%.0f"):format(temperature, temperaturethreshold))
-- Check if the temperature is below threshold - log as info with WARNING indicator
if temperature < temperaturethreshold and domoticz.data.notified == 0 then
	-- Set notification flag
	domoticz.data.notified = 1
	local msg = string.format('[WARNING] Heating Flow Temperature %.0f below threshold %.0f', temperature, temperaturethreshold)
	domoticz.log(msg, domoticz.LOG_INFO)
	-- Sent notification (log entry like Notification sent (email) => Success)
	domoticz.notify(msg)
else
	-- Reset notification flag
	domoticz.data.notified = 0
end
```
### Status
Not started.

## NEW: Integrate Outdoor Temperature & Humidity Devices (HmIP-STHO)
To measure the temperature and humidity in outdoor areas.
### Status
Not started.

## NEW: Virtual Sensor Switch (HmIP-PSM)
Describe how to create a virtual sensor type Switch On/Off to switch the HmIP-PSM via Domoticz Device On/Off Actions.
```
Domoticz is rather flexible, so look at below alternative:
Instead using Plugin, it is also possible via a virtual sensor switch or dzVents script.
Below an example for switching direct.

Get the datapoint ise_id of the psm device attribute state for channel as shown in the homematic webui.
Example: HMIP-PSM 0001D3C99C6AB3:3 Switch actuator

For this example, it is ise_id="1451" as taken from the statelist request (http://192.168.1.225/addons/xmlapi/statelist.cgi) 
<device name="Schalt-Mess-Steckdose MakeLab" ise_id="1418" unreach="false" config_pending="false">
...
               <channel name="HMIP-PSM 0001D3C99C6AB3:3" ise_id="1446" index="3" visible="true" operate="true">
               ...
                              <datapoint name="HmIP-RF.0001D3C99C6AB3:3.STATE" type="STATE" ise_id="1451" value="true" valuetype="2" valueunit="" timestamp="1612028617" operations="7"/>
               ...
               </channel>
...
</device>

The state has an attribute with value true or false

Change the state of the psm via XMLAPI request with ise_id=1451 and new_value true (=ON) or false (=OFF)
http://192.168.1.225/addons/xmlapi/statechange.cgi?ise_id=1451&new_value=true
With result:
<result>
<changed id="1451" new_value="true"/>
</result>

http://192.168.1.225/addons/xmlapi/statechange.cgi?ise_id=1451&new_value=false
<result>
<changed id="1451" new_value="false"/>
</result>

This can be used to change the state via for example dzVents script.

In Domoticz define:
New hardware, type Dummy. Give a name like VirtualSensors

Select the new hardware VirtualSensors and add click create virtual sensors.
Give a name, i.e. "PSM Switch A" and select sensor type switch.

From the Domoticz GUI, select tab switches and select the new switch "PSM Switch A".
Click edit.
Set On Action: http://192.168.1.225/addons/xmlapi/statechange.cgi?ise_id=1451&new_value=true
Set Off Action: http://192.168.1.225/addons/xmlapi/statechange.cgi?ise_id=1451&new_value=false
Save
Any try.

Note: Change of course the CCU URL address and the ise_id.
```
### Status
Not started.

## UPD: Gas Meter Counter Replace HmIP-FCI1
To replace the HmIP-FCI1 solution with Energy-Sensor-Gas and Counter-Sensor.
The HmIP-FCI1 solution has a high duty-cycle (50%) during cold days.
[ES-GAS-2](https://de.elv.com/elv-energy-sensor-gas-2-es-gas-2-156782?fs=3325670775)
[HM-ES-TX-WM](https://de.elv.com/elv-homematic-komplettbausatz-zaehlersensor-sendeeinheit-stromgas-hm-es-tx-wm-fuer-smart-home-hausautomation-140143)
### Status
Implemented a solution using an Arduino Nano with Reed switch and RF433 sender.
Monitoring accuracy.
