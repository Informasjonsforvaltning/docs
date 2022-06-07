---
title: SPARQL
weight: 3
---

data.norge.no har en [SPARQL](https://www.w3.org/TR/sparql11-overview/)-tjeneste som kan brukes for å søke i datakatalogen.

Endepunktet har følgende adresse: <https://sparql.fellesdatakatalog.digdir.no/>

Et enkelt web-grensesnitt for å sende spørringer til endepunktet finner du her: <https://data.norge.no/sparql>

### Eksempler på queries

For å få oversikt over hvilke egenskaper som finnes:

```shell
PREFIX dcat: <http://www.w3.org/ns/dcat#>
SELECT *
WHERE {​​​​​​
 ?dataset a dcat:Dataset .
  ?dataset ?prop ?value.
}​​​​​​
```

Deretter plukke og velge egenskaper:

```shell
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX purl: <http://purl.org/dc/terms/>
SELECT *
WHERE {​​​​​​​​​​​​​​
 ?dataset a dcat:Dataset .
 ?dataset purl:title ?title.
 ?dataset rdf:type ?type.
# Velg nye egenskaper ved: ?dataset <ønsket egenskap> ?egenskapsverdi
}​​​​​​​​​​​​​​​​​​​​​
```
