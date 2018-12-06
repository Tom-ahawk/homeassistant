# Homeassistant - Air Quality Measurement Sensor for Norway

"Air pollution - from traffic, industrial or natural sources – can have a major impact on the environment, human health and ecosystems at all scales. (Nilu)"

Sensor code for Home Assistant, using Nilu API for getting air quality measurement components/value from stations in Norway.

The Home Assistant sensor uses the Nilu API for getting pollution data from measurement stations scattered around Norway. Find the one closest to you (at www.luftkvalitet.info ) and get the air quality components with value and a health risk assessment (PM 2.5, PM10, NO2 etc.).

The code creates separate sensors for every station/component. In addition a sensor ending in ”_max” . This sensor has the component with the highest health risk.

Note, different stations can deliver different measurement components. The value scale for each component is individual when it comes to health risk. Meaning, components with the same value, does not necessarily represent the same health risk. Component/value is mapped to the health risk scale and is represented by the attributes “index/color/message”. Index 1 to 6 (-highest health risk), color code as represented at www.luftkvalitet.info.

Input parameters are “area” and “location”. Find your area/location at www.luftkvalitet.info

Example:
- platform: nilu
  region: Oslo,Manglerud
  
Add the nilu.py file your HA, to /config/custom_components/sensor/nilu.py
  
The code was initially developed by clyra, 
https://github.com/clyra/homeassistant/blob/master/custom_components/sensor/nilu.py
And slightly modified by me
