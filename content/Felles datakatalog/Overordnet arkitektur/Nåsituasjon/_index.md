---
title: Nåsituasjon
weight: 1
---

Her følger en kort oversikt over den overordnede arkitekturen til våre komponenter.
## Diagram
Sammenhengen mellom komponentene illustreres i følgende diagram:
![Overodnet nåsituasjons-arkitektur](overordnet_arkitektur_baseline.svg)

## Om komponentene i nåsituasjon
I dag har vi delt de ulike komponentene inn i en løsning for søk i kataloger, en løsning for registrering, en løsning for innhøsting (harvester). I tillegg har vi en intern komponent for referanse-data.

### Søkeløsningen
* search: Vår portal for søk på tvers av alle katalogene
* search-api: Eksternt api med oppslag mot datasettkatalogen.
* api-cat: Eksternt api med oppslag mot api-katakogen.
* concept-cat: Eksternt api med oppslag mot begreps-katalogen.

### Registreringsløsningen
* registration-react: Vårt brukergrensesnitt for å registrere og legge inn innhold i kataloger
* registration-api: backend-komponent for Registreringsløsningen
* registration-auth: komponent som håndterer innlogging via [IDPorten](https://eid.difi.no/nb/id-porten)

### Høsteløsningen
Høsteløsningen laster ned datakataloger og gjør dem søkbare. Består av

* harvester
* harvester-api

## Modellene

* Archi-modellen: https://github.com/Informasjonsforvaltning/SA_Informasjonsforvaltning_BASELINE
* Html-versjon: https://informasjonsforvaltning.github.io/SA_Informasjonsforvaltning_BASELINE/
