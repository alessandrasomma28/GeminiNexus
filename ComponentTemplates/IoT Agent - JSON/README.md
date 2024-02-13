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

## References

* [IoT Agent - JSON Github Repository](https://github.com/telefonicaid/iotagent-json)
* [FIWARE Tutorial for MQTT connection](https://github.com/FIWARE/tutorials.IoT-over-MQTT)
