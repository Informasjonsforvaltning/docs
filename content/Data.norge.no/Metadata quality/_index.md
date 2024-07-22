---
title: Metadata quality
weight: 7
---

```goat
                             +----------------+
                             | RabbitMQ       |
                             |                |
 .-----------------------.   |  +----------+  |   .-----------------.
| dataset-event-publisher |<-(--+ harvests |<-(--+ dataset-harvester |
 '-+---------------------'   |  +----------+  |   '-----------------'
   |                   ^     +----------------+     ^
   |                   |                            |
   |                    '--------------------------'
   |
   |  +-------------------------------------------------------------------------------+
   |  | Kafka                                                                         |
   |  |                                                                               |
   |  |  +----------------+ +--------------------+                    +------------+  |
    '-)->| dataset-events | | mqa-dataset-events |                    | mqa-events +--)-.
      |  +-------------+--+ +-----------------+--+                    +------------+  |  |
      |                |       ^              |                         ^             |  |
      +----------------)-------)--------------)-------------------------)-------------+  |
                       v       |              |                         |                |
                     .---------+-.            |    .----------------.   |                |
                    | assmentator |           +-->| property-checker +--+                |
                     '-----------'            |    '----------------'   |                |
                                              |    .----------------.   |                |
                                              +-->|   url-checker    +--+                |
                                              |    '----------------'   |                |
                                              |    .----------------.   |                |
                                               '->|  dcat-validator  +-'                 |
                                                   '----------------'                    |
                                                                                         |
                                       .--------.                                        |
                                      |          |                                       v
                                      |'--------'|     .-----------.      .---------------.
                                      | Postgres |<-->| scoring-api |<-->| scoring-service |
                                      |          |     '-----------'      '---------------'
                                       '--------'

```


[`dataset-event-publisher`](https://github.com/Informasjonsforvaltning/fdk-dataset-event-publisher)
listens for RabbitMQ harvest messages from
[`dataset-harvester`](https://github.com/Informasjonsforvaltning/fdk-dataset-harvester).
It then gets dataset-graphs from `dataset-harvester`,
and produces an event on the _dataset-events_ topic for every dataset `dataset-harvester` has updated.
[`assmentator`](https://github.com/Informasjonsforvaltning/fdk-mqa-assmentator)
consumes every harvested graph from _dataset-events_,
adds `hasAssessment` properties on both dataset- and distribution-nodes,
and produces a new event with the resulting graph on _mqa-dataset-events_.
[`property-checker`](https://github.com/Informasjonsforvaltning/fdk-mqa-property-checker),
[`url-checker`](https://github.com/Informasjonsforvaltning/fdk-mqa-url-checker) and [dcat-validator](https://github.com/Informasjonsforvaltning/fdk-mqa-dcat-validator)
will all three consume dataset graphs from _mqa-dataset-events_
and produce assessment graphs to _mqa-events_.
These assessment graphs is consumed by
[`scoring-service`](https://github.com/Informasjonsforvaltning/fdk-mqa-scoring-service),
and merges these based on _fdk_id_ and event timestamp.
`scoring-service` saves/updates assessment graphs in `Postgres` through
[`scoring-api`](https://github.com/Informasjonsforvaltning/fdk-mqa-scoring-api),
as well as total score for every dimension so that it is possible to execute quick aggregated queries.
