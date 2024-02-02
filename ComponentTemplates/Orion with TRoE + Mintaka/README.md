# Orion with Temporal Representation of Entities (TRoE) + Mintaka

This template is composed by the Orion-LD broker (and its Mongo database), a Timescale database for storing temporal data and Mintaka that exposes API for retrieving temporal data. 

To deploy this template, you need to run this:
```
docker-compose up -d
```
Make sure that the _docker-compose.yml_ and the _.env_ files are both in the same folder.

In this template, Orion has an option for the **Temporal Representation of Entities** (TRoE) that has been set-up in the environment parameters, so the context broker is saving also the temporal changes of the entities.
While Orion-LD takes care of populating the TRoE databases, another component handles the queries of temporal data - Mintaka. So, for queries of the temporal data, instead of sending the requests to Orion-LD, the queries are sent to Mintaka, 
which is exposed on its port (internal port 8082, mapped to 8027 in the docker-compose file)


## References

* [Mintaka Github Repository](https://github.com/FIWARE/mintaka)
* [Timescale Repository](https://fiware-orion.readthedocs.io/en/master/)
* [Timescale Database](https://www.timescale.com/)
