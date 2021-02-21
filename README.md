# HAP-Python-Photovoltaic
push SMA-Inverter Values to the Homekit, readable by Eve App

Based on HAP-Python and SBFSpot.
Older style SMA inverters my have readable Bluetooth interfaces. See the github SFBSpot project <https://github.com/SBFspot/SBFspot>, how to connect to the inverter and how to store inverter values into a SQLite database.
Under "/usr/local/lib/python3.x/dist-packages/pyhap/resources/" you will find predefined Homkit services and characteristics for using in the HAP-Python module as preloaded_service. (if you like, you can use the HAP-Python loader modules for loading sepeately)

## Installation

Create 3 Version 4 UUID's with "https://www.uuidgenerator.net" for one service and two characteristics. 

Extend services.json with:

>"PhotoVoltaic": {<br>
"OptionalCharacteristics": <br>
["Name"],<br>
"RequiredCharacteristics": [<br>
"YieldDay",<br>
"YieldYear"<br>
],<br>
"UUID": "your UUID"<br>
 }<br>
 >
 and characteristics.json with:
 <br>
> "YieldDay": {<br>
      "Format": "float",<br>
      "Permissions": [<br>
         "pr",<br>
         "ev"<br>
      ],<br>
      "UUID": "your UUID",<br>
      "unit": "Wh",<br>
          "maxValue": 100000,<br>
          "minValue": 0,<br>
          "minStep": 1<br>
   },<br>
   "YieldYear": {<br>
      "Format": "float",<br>
      "Permissions": [<br>
         "pr",<br>
         "ev"<br>
      ],<br>
      "UUID": "your UUID",<br>
      "unit": "kWh",<br>
      "maxValue": 100000000000,<br>
      "minValue": 0,<br>
      "minStep": 0.001<br>
   }<br>
 >
 
 
 Follow the HAP-Python installation steps by using Photovoltaic class.
 

