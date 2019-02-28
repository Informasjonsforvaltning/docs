---
title: Nåsituasjon
weight: 1
---

Her følger en kort oversikt over den overordnede arkitekturen til våre komponenter.
## Diagram
Sammenhengen mellom komponentene illustreres i følgende diagram:
<img src="./overordnet_arkitektur_baseline.svg" width="100%" alt="Overodnet nåsituasjons-arkitektur" align=center >

## Om komponentene i nåsituasjon
I dag har vi delt de ulike komponentene inn i en løsning for søk i kataloger, en løsning for registrering, en løsning for innhøsting (harvester). I tillegg har vi en intern komponent for referanse-data.

### Søkeløsningen
* search: Vår portal for søk på tvers av alle katalogene
* search-api: Eksternt api med oppslag mot datasettkatalogen. <small><a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/fdk.yaml" target="_blank">OpenAPI</a></small>
* api-cat: Eksternt api med oppslag mot api-katakogen. <small><a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/api-cat.yaml" target="_blank">OpenAPI</a></small>
* concept-cat: Eksternt api med oppslag mot begreps-katalogen. <small><a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/concept-cat.yaml" target="_blank">OpenAPI</a></small>

### Registreringsløsningen
* registration-react: Vårt brukergrensesnitt for å registrere og legge inn innhold i kataloger
* registration-api: backend-komponent for Registreringsløsningen
* registration-auth: komponent som håndterer innlogging via <a href="https://eid.difi.no/nb/id-porten" target="_blank">IDPorten</a>

### Høsteløsningen
Høsteløsningen laster ned datakataloger og gjør dem søkbare. Består av

* harvester
* harvester-api

## Modellene

* Archi-modellen: https://github.com/Informasjonsforvaltning/SA_Informasjonsforvaltning_BASELINE
* Html-versjon: https://informasjonsforvaltning.github.io/SA_Informasjonsforvaltning_BASELINE/
