# mqttTakFlow
Node-Red Flow to forward MQTT sensor location to ATAK via multicast or TAKServer. (used in conjunction with Ampledatas node-red-contrib-tak)

![flow](/mqttTakFlow.png?raw=true "Node Red Flow")

SETUP NODE-RED:

-https://nodered.org/docs/getting-started/

-options include installing node-red on your local PC, a Raspberry Pi or similar single board computer or mini PC, deploying node-red on a cloud server or virtual private server (VPS), Docker Container, or local virtual environment. After installing node-red you should be able to go to the node-red dashboard at http://node-red-ip-address:1880 you may have to open appropriate ports (1880) to allow devices to access the node-red dashboard.

-ensure you install the "node-red-contrib-tak" node. If not there should be a prompt when you import mqttTakFlow in Node-Red that there are nodes that need to be installed and will automatically install them for you if you allow. In the event that isnt the case, in Node-Red: Menu (3 horizontal lines) > Manage palette > Install > Search "node-red-contrib-tak" > Install > Install

----------------------------------------------

IMPORT .JSON FLOW TO NODE RED:

-in GitHub: click on "mqttTakFlow.json" > click on the download icon "Download raw file" > note where the "mqttTakFlow.json" file downloaded to, default is in your Downloads folder.

-in Node-Red: click on menu icon (3 horizontal lines top right) > click on "Import" > click on "select a file to import" > go to Downloads folder and click on "mqttTakFlow.json" > Upload > Import

ALTERNATIVELY..

-you can just copy the whole "mqttTakFlow.json" code from GitHub and paste it into the Node-Red Import Clipboard.

-----------------------------------------------

MQTT PUB PAYLOAD EXAMPLE (JSON):

    {

        "id": "1234",
    
        "name": "test-1234",
    
        "lat": "20.2020",
    
        "lon": "40.4040"
    
    }

-------------------------------------------

MQTT PUB PAYLOAD:

-the "id" key gets used as the uid for the CoT msg so only one Marker populates on the map for your mqtt device.

-the "name" key gets used as the name of the CoT marker on TAK.

-the "lat" and "lon" key is used to plot the latitude and longitude coordinates, however you get the lat and lon of your mqtt device (gps module, network gps, virtual gps, etc.) be sure to pass them seperately as a "lat" and "lon" key.

--------------------------------------------

MQTT IN NODE:

-configure the "mqtt in" node of the necessary subscribed topic and the authentication needed (if necessary).

-------------------------------------------------

TROUBLESHOOTING / KNOWN ISSUES:

-in the event the Node-Red service explodes and you lose connection to the Node-Red UI and cant reconnect, you may need to restart your Node-Red service

$ sudo service node-red restart
