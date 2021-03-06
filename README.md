# Home Assistant - Air Quality Measurement Sensor for Norway

"Air pollution - from traffic, industrial or natural sources – can have a major impact on the environment, human health and ecosystems at all scales." Nilu- Norsk institutt for luftforskning (Norwegian Institute for Air Research).

Sensor code for Home Assistant, using Nilu API, for getting air quality measurement components/value from stations scattered around Norway.

Find the stations(s) closest to you at www.luftkvalitet.info , and get the air quality components (PM 2.5, PM10, NO2 etc.) with value and a health risk assessment.

The code creates separate sensors for every station/component. In addition a sensor ending in ”_max” . The MAX-sensor has the component with the highest health risk.

Note, different stations can deliver different measurement components. The value scale for each component is individual when it comes to health risk. Meaning, components with the same value, does not represent the same health risk. Component/value is mapped to the health risk scale and is represented by the attributes “index" (1 to 6-highest health risk) / "color" / "message" (Low/Moderate/Significant/Serious health risk).

Input parameters are “area” and “location”. Find your area/location at www.luftkvalitet.info

Example:
- platform: nilu
  region: Oslo,Manglerud
  
Add the nilu.py file to /config/custom_components/sensor/nilu.py
  
The code was initially developed by @clyra, and slightly modified by me.
https://github.com/clyra/homeassistant/blob/master/custom_components/sensor/nilu.py

