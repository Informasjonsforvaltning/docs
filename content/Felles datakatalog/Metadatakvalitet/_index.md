---
title: Metadatakvalitet
weight: 7
---

```goat
                             +----------------+
                             | RabbitMQ       |
                             |                |
 .-----------------------.   |  +----------+  |   .-----------------.
| dataset-event-publisher |<-(--+ harvests |<-(--| dataset-harvester |
 '-+---------------------'   |  +----------+  |   '-----------------'
   |                   ^     +----------------+     ^
   |                   |                            |
   |                    '--------------------------'
   |
   |  +-------------------------------------------------------------------------------+
   |  | Kafka                                                                         |
   |  |                                                                               |
   |  |  +----------------+ +--------------------+                    +.-----------+  |
    '-)->| dataset-events | | mqa-dataset-events |                    | mqa-events +--)-.
      |  +-------------+--+ +-----------------+--+                    +------------+  |  |
      |                |       ^              |                         ^             |  |
      +----------------)-------)--------------)-------------------------)-------------+  |
                       v       |              |                         |                |
                     .---------+-.            |    .----------------.   |                |
                    | assmentator |           +-->| property-checker +--+                |
                     '-----------'            |    '----------------'   |                |
                                              |    .----------------.   |                |
                                               '->|   url-checker    +-'                 |
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
lytter etter RabbitMQ harvest meldinger fra
[`dataset-harvester`](https://github.com/Informasjonsforvaltning/fdk-dataset-harvester).
Den henter så datasett-grafer via apiet til `dataset-harvester`,
og produserer én event på _dataset-events_ topicen for hvert datasett `dataset-harvester` har oppdatert.
[`assmentator`](https://github.com/Informasjonsforvaltning/fdk-mqa-assmentator)
konsumerer hver høstet graf fra _dataset-events_,
legger til `hasAssessment` properties på både dataset- og hver distribution-node,
og produserer videre til _mqa-dataset-events_.
[`property-checker`](https://github.com/Informasjonsforvaltning/fdk-mqa-property-checker) og
[`url-checker`](https://github.com/Informasjonsforvaltning/fdk-mqa-url-checker)
konsumerer begge datasett grafer fra _mqa-dataset-events_
og produserer assessment grafer til _mqa-events_.
Disse assessment grafene konsumeres av
[`scoring-service`](https://github.com/Informasjonsforvaltning/fdk-mqa-scoring-service),
og sammenslås basert på _fdk_id_ og event timestamp.
`scoring-service` lagrer/oppdaterer assessment grafer i `Postgres` via
[`scoring-api`](https://github.com/Informasjonsforvaltning/fdk-mqa-scoring-api),
samt totalscore for hver dimensjon for å kunne gjøre raske aggregerte spørringer.
