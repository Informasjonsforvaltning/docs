---
title: API
weight: 3
---
Her følger en kort beskrivelse begrepskatalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).

## Detaljer

* Server: `https://fellesdatakatalog.digdir.no`
* Tilbyr: `application/json`

| Oppføring i API-katalogen |
| ---- |
| TBD |

## Eksempel på spørringer

Alle begrep:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts"
```

Et spesifikt begrep basert på id:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts/<id>"
```

Et  enkelt søk etter begrep med ordet "innsyn":

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts?q=innsyn"
```

En spørring som gir filter på organisasjonen (i eksempelet Brønnøysundregistrene) som har publisert begrepet:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/concepts?orgPath=/STAT/912660680/974760673"
```

Tilgang til registreringsløsningens samling av publiserte begreper som <a href="https://doc.difi.no/data/begrep-skos-ap-no/" target="_blank"><u>SKOS-AP-NO</u></a>:

```Shell
curl -H "Accept: text/turtle" https://registrering-begrep-api.fellesdatakatalog.digdir.no/collections
```

Som over, men for ein gitt organisasjon (publisher):

```Shell
curl -H "Accept: text/turtle" "https://registrering-begrep-api.fellesdatakatalog.digdir.no/collections?publisher=991825827"
```
