---
title: API
weight: 2
---
Her følger en kort beskrivelse API-katalogens API, samt eksempel på bruk med <a href="https://curl.haxx.se/" target="_blank">curl</a>.
## Detaljer
* Server: `https://fellesdatakatalog.brreg.no`
* Tilbyr: `application/json`

| <a href="https://fellesdatakatalog.brreg.no/apis/77bb65c6-38f7-4eab-80c7-855d45aaa996" target="_blank"><u>Oppføring i API-katalogen</u></a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/api-cat.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle API-er:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis
```
Et spesifikt API basert på id:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis/<id>
```
En  enkelt søk etter API-er med ordet "barnehage":
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis?q=barnehage
```
Liste alle API-er der utgiver er Registerenheten i Brønnøysund:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis?orgPath=/STAT/912660680/974760673
```
Liste endepunkter til alle API-er som realiserer en gitt tjenestetype:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis/endpoints?serviceType=Kontoopplysninger
```
Liste endepunkter til alle API-er som realiserer en gitt tjenestetype for gitte organisasjonsnummer:
```
curl -H "Accept: application/json" https://fellesdatakatalog.brreg.no/api/apis/endpoints?serviceType=Kontoopplysninger&orgNos=910244132,910888447
```
