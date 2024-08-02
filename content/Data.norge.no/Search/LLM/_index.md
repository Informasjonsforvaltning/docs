---
title: LLM
weight: 2
---

The service is responsible for handling AI LLM searches is [fdk-llm-search-service](https://github.com/Informasjonsforvaltning/fdk-llm-search-service), which is described by [this OpenAPI specification](
    https://aisearch.api.fellesdatakatalog.digdir.no/swagger-ui/index.html
).

### Environments

- Production endpoint: <https://aisearch.api.fellesdatakatalog.digdir.no/llm> (not yet available)
- Demo endpoint: <https://aisearch.api.demo.fellesdatakatalog.digdir.no/llm> (not yet available)
- Staging endpoint: <https://aisearch.api.staging.fellesdatakatalog.digdir.no/llm>

### Querying

Simple example using the staging endpoint:
```Shell
curl -X POST 'https://aisearch.api.staging.fellesdatakatalog.digdir.no/llm' -H 'Content-Type: application/json' -d '{"query":"Data about birds living in Norway"}'
```

The results should look like this:
```Shell
{
  "hits": [
    {
      "id": "d69e69bb-7572-3979-9298-d0bd1f4552fd",
      "title": "SEAPOP Estimerte hekkebestander for sjøfugl",
      "description": "Dette datasettet inneholder estimerte hekkebestander for sjøfugl i Norge.",
      "type": "DATASET",
      "publisher": "Norsk institutt for naturforskning",
      "publisherId": "950037687"
    },
    {
      "id": "13f37cd2-8278-3812-b4cf-c2c9fcd7447a",
      "title": "SEAPOP Bestander for sjøfugl i åpent hav - vintersesong",
      "description": "Dette datasettet inneholder bestander for sjøfugl i åpent hav i Norge i vintersesongen.",
      "type": "DATASET",
      "publisher": "Norsk institutt for naturforskning",
      "publisherId": "950037687"
    },
    {
      "id": "71c897bf-370a-3cd7-b5d1-f7485c773ec3",
      "title": "SEAPOP Bestander for sjøfugl i åpent hav - høstsesong",
      "description": "Dette datasettet inneholder bestander for sjøfugl i åpent hav i Norge i høstsesongen.",
      "type": "DATASET",
      "publisher": "Norsk institutt for naturforskning",
      "publisherId": "950037687"
    },
    {
      "id": "9ca54865-8fcb-3f59-bbc5-c44bbbf10f04",
      "title": "SEAPOP Bestander for sjøfugl i åpent hav - sommersesong",
      "description": "Dette datasettet inneholder bestander for sjøfugl i åpent hav i Norge i sommersesongen.",
      "type": "DATASET",
      "publisher": "Norsk institutt for naturforskning",
      "publisherId": "950037687"
    }
  ]
}
```
#### Limitations

The service returns maximum 7 results. This is due to performance and size of the prompt. This number can change in the future while new models become faster.

The service expects to find datasets. In order to get the best results we recommend to query for specific type of data and not general questions like "What time does the sun rise?".
