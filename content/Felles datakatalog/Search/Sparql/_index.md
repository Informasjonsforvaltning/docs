---
title: SPARQL
weight: 3
---

[Read more about SPARQL here](https://www.w3.org/TR/sparql11-overview/).

Production endpoint: <https://sparql.fellesdatakatalog.digdir.no>
Demo endpoint: <https://sparql.demo.fellesdatakatalog.digdir.no>
Staging endpoint: <https://sparql.staging.fellesdatakatalog.digdir.no>

Simple example using the staging endpoint:
```Shell
curl -X POST 'https://sparql.staging.fellesdatakatalog.digdir.no/?query=SELECT%20%2A%20WHERE%20%7B%20?sub%20?pred%20?obj%20.%20%7D%20LIMIT%201'
```

Data.norge.no has a simple GUI for SPARQL queries:
- production <https://data.norge.no/sparql>
- demo <https://demo.fellesdatakatalog.digdir.no/sparql>
- staging <https://staging.fellesdatakatalog.digdir.no/sparql>

### Query examples

List all properties and objects where the subject is this dataset <https://staging.fellesdatakatalog.digdir.no/datasets/04edc67b-046c-37a8-9822-29f03d2f1e80>:

```shell
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX dct: <http://purl.org/dc/terms/>

SELECT ?property ?object

WHERE {​​​​​​
  ?dataset a dcat:Dataset .
  ?record foaf:primaryTopic ?dataset .
  ?record a dcat:CatalogRecord .
  ?record dct:identifier "04edc67b-046c-37a8-9822-29f03d2f1e80" .
  ?dataset ?property ?object .
}​​​​​​
```

List all dataset titles:

```shell
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX dct: <http://purl.org/dc/terms/>

SELECT ?title

WHERE {​​​​​​​​​​​​​​
 ?dataset a dcat:Dataset .
 ?dataset dct:title ?title .
}​​​​​​​​​​​​​​​​​​​​​
```
