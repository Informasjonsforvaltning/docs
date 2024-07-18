---
title: Harvesters
weight: 2
---

* [fdk-concept-harvester](https://github.com/Informasjonsforvaltning/fdk-concept-harvester)
* [fdk-dataservice-harvester](https://github.com/Informasjonsforvaltning/fdk-dataservice-harvester)
* [fdk-dataset-harvester](https://github.com/Informasjonsforvaltning/fdk-dataset-harvester)
* [fdk-event-harvester](https://github.com/Informasjonsforvaltning/fdk-event-harvester)
* [fdk-informationmodel-harvester](https://github.com/Informasjonsforvaltning/fdk-informationmodel-harvester)
* [fdk-public-service-harvester](https://github.com/Informasjonsforvaltning/fdk-public-service-harvester)

The harvest process is triggered by messages from RabbitMQ with the routing key `*.#.HarvestTrigger`, where * is the relevant resource type, ie dataset, and # is an unused part of the key. The unused part of the key was in earlier versions used to supply the id of a publisher, this has since been moved to the message body, see “publisherId” in the next section.

The body of the trigger message has 3 relevant parameters:
* **dataSourceId** - Triggers the harvest of a specific source from fdk-harvest-admin
* **publisherId** - Triggers the harvest of all sources for the specified organization number.
* **forceUpdate** - Indicates that the harvest should be performed, even when no changes are detected in the source

A triggered harvest will download all relevant sources from fdk-harvest-admin, download everything from the source and try to read it as a RDF graph via a jena Model. If the source is successfully parsed as a jena Model it will be compared to the last harvest of the same source. The harvest process will continue if the source is not isomorphic to the last harvest or forceUpdate is true.

All blank nodes will be [skolemized](https://www.w3.org/wiki/BnodeSkolemization) in the resource graphs, which means that an URI is generated for the blank node.

When all sources from the trigger has been processed a new rabbit message will be published with the routing key `*.harvested`, the message body will be a list of harvest reports, one report for each source from [fdk-harvest-admin](https://informasjonsforvaltning.github.io/data.norge.no/harvesting/harvest-admin).
Each report will contain these fields:
* **id** - the id for the source in fdk-harvest-admin
* **url** - the source url
* **dataType** - the relevant resource type
* **harvestError** - a boolean wich is set to true if the harvest failed
* **startTime** - the timestamp when the harvest started
* **endTime** - the timestamp when the harvest finished
* **errorMessage** - eventual error message if the harvest failed
* **changedCatalogs** - fdkId and uri for each catalog with changes
* **changedResources** - fdkId and uri for each resource with changes
* **removedResources** - fdkId and uri for each resource removed from the source

Since subsequent part of the harvest process is dependent of kafka events, the services deployed from [fdk-kafka-event-publisher](https://github.com/Informasjonsforvaltning/fdk-kafka-event-publisher) will listen for harvest reports in rabbitMQ and produce kafka events for removed and changed resources.
