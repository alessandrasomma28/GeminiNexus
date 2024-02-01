# FIWARE Orion-LD Context Broker
This template is only composed by Orion context broker - in the LD version - and the associated database (MongoDB). 
Note that Orion needs its database to function properly.

To deploy this template, you need to run this:
```
docker-compose up -d
```
Make sure that the _docker-compose.yml_ and the _.env_ files are both in the same folder.

_Note_: This template is configured without any option of Temporal Representation of Entities (TRoE), so the context broker is only saving the actual state of the entities.

## References

* [Orion-LD Github Repository](https://github.com/FIWARE/context.Orion-LD)
* [Orion-LD Documentation](https://fiware-orion.readthedocs.io/en/master/)
