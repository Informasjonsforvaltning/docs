---
title: API
weight: 2
---
Her følger en kort beskrivelse datasett-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).
## Detaljer
* Server: `https://fellesdatakatalog.brreg.no`
* Tilbyr: `application/json`

| <a href="https://fellesdatakatalog.brreg.no/apis/bff198ab-faef-4b31-89b2-348a0bf1336e" target="_blank"><u>Oppføring i API-katalogen</u></a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/fdk.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle datasett:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/datasets
```
Alle datasett med "paginering", returnerer første side:
```
curl -H "Accept: application/json" 'http://fellesdatakatalog.brreg.no/api/datasets?page=0'
```
Et spesifikt datasett basert på id:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis/<id>
```
En  enkelt søk etter datasett med ordet "barnehage":
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/datasets?q=barnehage
```
