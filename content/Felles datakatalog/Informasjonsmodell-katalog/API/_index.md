---
title: API
weight: 2
---
Her følger en kort beskrivelse informasjonsmodell-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/)..

## Detaljer

* Server: `https://fellesdatakatalog.digdir.no/api/informationmodels`
* Tilbyr: `application/json`

| Oppføring i API-katalogen |
| ---- |
| <https://data.norge.no/dataservices/6efe3d09-44d8-3f15-b812-efad16cb7132> |

## Eksempel på spørringer

Alle informasjonsmodeller:

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels
```

En spesifik informasjonsmodell basert på id:

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels/<id>
```

En  enkelt søk etter modeller med ordet "summert":

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels?q=summert
```
