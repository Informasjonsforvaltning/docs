---
title: API
weight: 2
---

Her følger en kort beskrivelse API-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/).

## Detaljer

- Server: `https://fellesdatakatalog.digdir.no`
- Tilbyr: `application/json`

| Oppføring i API-katalogen |
| ---- |
| <https://data.norge.no/dataservices/b9cf5ca7-7acf-3fd9-b7ff-4167adb84a83> |

## Eksempel på spørringer

Alle API-er:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis"
```

Et spesifikt API basert på id:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis/<id>"
```

En enkelt søk etter API-er med ordet "barnehage":

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis?q=barnehage"
```

Liste alle API-er der utgiver er Registerenheten i Brønnøysund:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis?orgPath=/STAT/912660680/974760673"
```

Liste endepunkter til alle API-er som realiserer en gitt tjenestetype. Merk: "environment" er obligatorisk og må enten vere "test" eller "production"

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis/endpoints?serviceType=Kontoopplysninger&environment=production"
```

Liste endepunkter til alle API-er som realiserer en gitt tjenestetype for gitte organisasjonsnummer:

```Shell
curl -H "Accept: application/json" "https://fellesdatakatalog.digdir.no/api/apis/endpoints?serviceType=Kontoopplysninger&orgNos=984851006,837884942&environment=production"
```
