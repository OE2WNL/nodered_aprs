# Send Weatherdata via Node-Red
Collect weatherdata from your weatherstation and send it via Nodered in the APRS Network

* Install Node-Red i.e. on a Raspberry https://nodered.org/docs/getting-started/raspberrypi
* Import the flows_APRS_Weather.json file via Import -> select file
* You will see 4 nodes

![Nodes](https://github.com/OE2WNL/nodered_aprs/raw/main/nodes.png)
* Open the "configure" node and change the settings for your call, location etc.

### Fetch weatherdata from your weatherstation
This part varies depending what weatherstation you have and how you get the data.
i.e. Netatmo has an API to fetch the sensor values, others just query their Arduino with a BMP-180 sensor.
You need to provide the following sensor values at the given variable's with the given unit:


| variable | unit | remark |
|---|---|---|
| msg.payload.windDir | degrees | wind direction  |
| msg.payload.windSpeed | km/h | wind speed |
| msg.payload.windGust  | km/h | wind maximum in the last 5 min |
| msg.payload.temperature  | °C | temperature |
| msg.payload.rainLastHour  | mm | rain since the last hour |
| msg.payload.rainLast24  | mm | rain within the last 24h |
| msg.payload.rainSinceMidnight | mm | rain since midnight |
| msg.payload.humidity  | % | humidity |
| msg.payload.pressure  | mbar | pressure |


Please see the APRS Protocol Reference PDF where you'll find in Chapter 12 detailed explanation for the APRS weather packet:
ftp://ftp.tapr.org/aprssig/aprsspec/spec/aprs101/APRS101.pdf
