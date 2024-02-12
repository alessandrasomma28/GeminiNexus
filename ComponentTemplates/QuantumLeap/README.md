# QuantumLeap - time-series data management

This Template consists of the following components: 
* **Orion-LD Context Broker** for managing context entities.
* **MongoDB** for persisting actual state of the entities.
* **Timescale** database (based on PostgreSQL) for persisting time-series data.
* **QuantumLeap** service used for storing, querying and retrieving NGSI v2 and NGSI-LD spatial-temporal data. QuantumLeap converts NGSI semi-structured data into tabular format and stores it in a time-series database, associating each database record with a time index.
* **Redis**, a key-value store used by QuantumLeap as a cache (mainly for metadata linked to NGSI entities).
* **Grafana** service used for display the persisted time-series data (either in CrateDB or in Timescale).
* **quantum-db-setup** is a container that runs a process for setting up the database inside Timescale.

To deploy this template, you need to run this:
```
docker-compose up -d
```
Make sure that the _docker-compose.yml_ and the _.env_ files are both in the same folder.

QuantumLeap needs to be connected to at least one time-series DBs. It supports both CrateDB and Timescale (with PostGIS extension) for storing time-series data. To reduce queries to DBs, QuantumLeap uses a caching system: for now the only cache backend supported is Redis. 
For more details about how interaction between QuantumLeap and the mentioned DBs works refer to the original docs available here: [QuantumLeap Docs](https://quantumleap.readthedocs.io/en/stable/)

## Subscription Mechanism - Demo

<!-- TO DO: add images for Grafana connection and in general more details to this demo -->

In this folder is available a jupyter notebook, which name is _subscription-demo.ipynb_. Using this notebook is possible to test the subscription mechanism. After setting up the subscription and making some updates to the registered entities, 
it's possible to view the temporal data using Grafana service addressed in http://localhost:3000).

_Note_: on the first access (made with the username/password: admin/admin), Grafana ask you to set a new password for the admin user. 

Once logged, a data source has to be set (follow the guidline here: [Grafana Datasource Configuration](https://quantumleap.readthedocs.io/en/stable/admin/grafana/)). Unlike the CrateDB configuration, the Database name is 'quantumleap' and the user set is 'postgres' 
(according to the environment parameters set into the docker-compose file)

![setup](https://github.com/alessandrasomma28/GeminiNexus/assets/86465812/1d5d3be4-f59a-43b1-9bcf-1c75ae9df6d1)

Once linked the data source, it's possible to explore the data using the 'Explore' button (the bar on the left side) and to make some Dashboard (Create -> Dashboard).

![explore1](https://github.com/alessandrasomma28/GeminiNexus/assets/86465812/386fe19c-6b23-495b-bf94-33aa416e2d75)
## References

* [Timescale Repository](https://fiware-orion.readthedocs.io/en/master/)
* [Timescale Database](https://www.timescale.com/)
* [QuantumLeap Repository](https://github.com/FIWARE-GEs/quantum-leap)
* [QuantumLeap Docs](https://quantumleap.readthedocs.io/en/latest/)
* [Grafana Website](https://grafana.com/)
