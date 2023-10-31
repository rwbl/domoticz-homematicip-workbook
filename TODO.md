# domoticz-homematicip-workbook - TODO.md
Actions to consider implementing in the next version of the workbook.
Any ideas to be captured in IDEAS.md.

## NEW: Heating Unit Flow Temperature Threshold
Set a low threshold for the **T1 Vorlauf** temperature to check if the Heating Unit is working.
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

## NEW: Explore Advanced Usage CuxD.
### Status
Not started.

## UPD: e-Paper Display Special Characters
How to display the character used to display a special character.
Example how to display the "[ or ]" characters.
### Status
Not started.

## NEW: Alert Indicator (HmIP-MOD-OC8) Raspberry Pi Pico
Build the MicroController solution with a Raspberry Pi Pico with MicroPython instead an Arduino with B4R.
### Status
Not started.

## Custom Pages
* Explore buttons 'copy', 'csv' and other.
* Show notify Toastmessage immediate in foreground instead of background
* Dialog textarea containing a datapoint with attributes
* Test foreach over table rows
* Page to run a specific program using XML-API runprogram.cgi?program_id=1234 and capture the output
### Status
Not started.

## NEW: Pluggable Switch Timer
Use a timer, in dzVents, to set the start & stop time of a pluggable switch.
This could be used to control a Domoticz Dashboard System to maintain the battery.
### Status
Not started.

## NEW: Explore Dashboards
Explore alternative dashboards for Domoticz. 
[Dashtics](https://www.domoticz.com/wiki/Dashticz)
[HomeHabit Dashboard](https://play.google.com/store/apps/details?id=app.homehabit.view&hl=gsw&gl=US)

### Status
Not started.
