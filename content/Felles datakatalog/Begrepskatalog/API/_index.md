---
title: API
weight: 3
---
Her følger en kort beskrivelse begrepskatalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).
## Detaljer
* Server: `https://fellesdatakatalog.digdir.no`
* Tilbyr: `application/json`

| <a href="https://fellesdatakatalog.digdir.no/dataservices/cb6483b8-4d94-473d-a4b9-8ee64abb9b91" target="_blank"><u>Oppføring i API-katalogen</u></a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/concept-cat.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle begrep:
```
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts"
```
Et spesifikt begrep basert på id:
```
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts/<id>"
```
Et  enkelt søk etter begrep med ordet "innsyn":
```
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts?q=innsyn"
```
En spørring som gir filter på organisasjonen (i eksempelet Brønnøysundregistrene) som har publisert begrepet:
```
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts?orgPath=/STAT/912660680/974760673"
```
Tilgang til registreringsløsningens samling av publiserte begreper som <a href="https://doc.difi.no/data/begrep-skos-ap-no/" target="_blank"><u>SKOS-AP-NO</u></a>:
```
curl -H "Accept: text/turtle" https://registrering-begrep-api.fellesdatakatalog.digdir.no/collections
```
Som over, men for ein gitt organisasjon (publisher):
```
curl -H "Accept: text/turtle" "https://registrering-begrep-api.fellesdatakatalog.digdir.no/collections?publisher=991825827"
```
