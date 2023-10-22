# Background
This code was originally forked from https://github.com/sam43434/remootio.

# Changes
Have had to make changes to account for the aioremootio library dependancies being out of date and in conflict with those required by Home Assistant. Instructions on how to fix this were posted here https://community.home-assistant.io/t/remootio-garage-door-automation-new-product/110559/109 and here https://github.com/sam43434/remootio/issues/12.

Instructions below to fix remootio to work with HA 7.3

1. Go to github and fork the aioremootio repo https://github.com/ivgg-me/aioremootio
2. Edit the requirements.txt file in your own aioremootio fork and change to below versions
        aiohttp==3.8.5
        pycryptodome==3.17
        async-class==0.5.0
        voluptuous==0.13.1
3. Go to your HA /config/custom_components/remootio/
4. Edit manifest.json file and change the line with requirements to look like the below, but change GITHUBUSERID to yours
        "requirements": ["aioremootio @ git+https://github.com/GITHUBUSERID/aioremootio.git"],
5. Don't redownload remootio HACS Otherwise you will overwrite your changes done in step 3
6. Restart HA and you should be good to go

# Original README.md
To use this integration with your Remootio device it has to be connected to your Wi-Fi, must have a fixed IP address assigned and a status sensor installed. Furthermore the API access must be enabled on the device.\n\nTo enable the API access on the device you need to access the device using the master key via the Remootio app, afterwards go to the _Websocket API_ settings in the _Device software_ section of the device settings and enbale the API with logging.\nAfter enabling the API the app will display the device's IP address and the credentials needed for API access.\n\nPlease enable the API on your Remootio device and enter the IP address and credentials shown by the app. Instead of the IP address you can also enter the host name of your Remootio device if you have configured one on your router or DNS server for it."

original creator: ivgg-me,   Temp repo setup until this makes it into the main core one day 
