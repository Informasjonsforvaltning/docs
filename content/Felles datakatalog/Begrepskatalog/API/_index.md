---
title: API
weight: 3
---
Her følger en kort beskrivelse begrepskatalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).
## Detaljer
* Server: `https://fellesdatakatalog.brreg.no`
* Tilbyr: `application/json`

| <a href="https://fellesdatakatalog.brreg.no/apis/cb6483b8-4d94-473d-a4b9-8ee64abb9b91" target="_blank"><u>Oppføring i API-katalogen</u></a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/concept-cat.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle begrep:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/concepts
```
Et spesifikt begrep basert på id:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/concepts/<id>
```
En  enkelt søk etter begrep med ordet "innsyn":
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/concepts?q=innsyn
```