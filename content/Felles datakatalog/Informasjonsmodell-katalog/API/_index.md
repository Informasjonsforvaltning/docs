---
title: API
weight: 2
---
Her følger en kort beskrivelse informasjonsmodell-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).
## Detaljer
* Server: `https://fellesdatakatalog.brreg.no/api/informationmodels`
* Tilbyr: `application/json`

| <a>Oppføring i API-katalogen</a> | <a>Lenke direkte til spesifikasjon (openAPI v3)</a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle informasjonsmodeller:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/informationmodels
```
En spesifik informasjonsmodell basert på id:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/informationmodels/<id>
```
En  enkelt søk etter modeller med ordet "summert":
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/informationmodels?q=summert
```
