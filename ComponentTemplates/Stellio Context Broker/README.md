# Stellio Context Broker
This template presents Stellio as a Context Broker compliant with the NGSI-LD standard. Unlike Orion-LD, Stellio also stores historical data via a time-series database. As the official documentation states, Stellio is composed of 2 business services:
* _search-service_: is in charge of handling the requests for the Core and Temporal APIs. It is backed by a PostgreSQL database, extended with the TimescaleDB and PostGIS extensions.
* _subscription-service_: is in charge of handling the requests for the Subscription API. It is backed by a PostgreSQL database, extended with the PostGIS extension.
  
In addition, the broker is equipped with an API Gateway component that simply forwards the incoming requests to one of the downstream services, based on the request path. Finally a Kafka streaming engine is used for decoupling communication inside the broker (and allowing to plug other services seamlessly)
## References
[Stellio Context Broker](https://stellio.readthedocs.io/en/latest/index.html)
