# IoT Agent - JSON Version
This template shows how IoT Agent works as an interface for devices with Orion Context Broker. The template consists of IoT Agent in the JSON version, Orion-LD Context Broker and MongoDB as the database for the persistence of both IoT Agent and Orion data. 
Furthermore, a _docker-compose_ file is provided for the deployment of Mosquitto as an MQTT broker.

To deploy this template, you need to run this:
```
docker-compose up -d
```
Make sure that the _docker-compose.yml_ and the _.env_ files are both in the same folder.

To deploy Mosquitto, move to the dedicated folder, i.e. docker-mosquitto, and run the same deployment command. Make sure that the _docker-compose.yml_ and _mosquitto.conf_ files are both in the same folder.

Note: the mosquitto _docker-compose_ file is built to be deployed after the IoT Agent template, since its container is based on the latter's network.

## HTTP / MQTT Northbound communication - Demo
In this folder is available a jupyter notebook, which name is demo-iotagent.ipynb_. The demo shows the connection and provisioning process required to enable northbound communication from the devices to the context broker using HTTP and MQTT protocols.

* HTTP communication: within the notepad, an HTTP message is sent to IoT Agent (on Northbound port 7896) in order to simulate an HTTP communication from a device.
* MQTT communication: an MQTT broker (e.g. the mosquitto docker container available [here](https://github.com/alessandrasomma28/GeminiNexus/tree/main/ComponentTemplates/IoT%20Agent%20-%20JSON/docker-mosquitto)) is deployed to interact with IoT Agent. The latter should be configured appropriately via the environment variables set in the _docker-compose_ file to connect to the broker. Finally, the device is emulated by sending an MQTT message via a client (e.g., _mosquitto_pub_) to the broker, which will in turn communicate with the IoT Agent.

## References

* [IoT Agent - JSON Github Repository](https://github.com/telefonicaid/iotagent-json)
* [FIWARE Tutorial for MQTT connection](https://github.com/FIWARE/tutorials.IoT-over-MQTT)
* [Eclipse Mosquitto MQTT Broker](https://mosquitto.org/)
