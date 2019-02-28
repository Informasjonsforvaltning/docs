---
title: API
weight: 2
---
Her følger en kort beskrivelse informasjonsmodell-katalogens API, samt eksempel på bruk med <a href="https://curl.haxx.se/" target="_blank">curl</a>.
## Detaljer
* Server: `https://fellesdatakatalog.brreg.no/api/informationmodels`
* Tilbyr: `application/json`

| <a>Oppføring i API-katalogen</a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/informationmodel-cat.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
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
