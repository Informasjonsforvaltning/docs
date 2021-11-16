---
title: API
weight: 2
---
Her følger en kort beskrivelse datasett-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).

## Detaljer

* Server: `https://fellesdatakatalog.digdir.no`
* Tilbyr: `application/json`

| Oppføring i API-katalogen |
| ---- |
| <https://data.norge.no/dataservices/04c03d38-d856-3dea-9278-ae3de6b850fb> |

## Eksempel på spørringer

Alle datasett:

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/datasets
```

Alle datasett med "paginering", returnerer første side:

```Shell
curl -H "Accept: application/json" 'https://fellesdatakatalog.digdir.no/api/datasets?page=0'
```

Et spesifikt datasett basert på id:

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/datasets/<id>
```

En  enkelt søk etter datasett med ordet "barnehage":

```Shell
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/datasets?q=barnehage
```
