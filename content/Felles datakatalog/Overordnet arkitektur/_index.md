---
title: Overordnet arkitektur
weight: 2
---

Her følger en kort oversikt over den overordnede arkitekturen til våre komponenter.

## TOGAF
Vi følger en tilpasset versjon av TOGAFs ADM metodikk når vi jobber med arkitektur. Dette betyr at vi tar fram både baseline (Nåsituasjon) og target (Målbilde) modeller, og ut i fra disse utarbeider vi transisjoner og migrasjonsplaner. Transisjons-arkitekturer er å finne i målbildet.

## ArchiMate
Våre arkitekturmodeller er laget i henhold til [Archimate-rammeverket](http://pubs.opengroup.org/architecture/archimate3-doc/) med hjelp av verktøyet [Archi](https://www.archimatetool.com/). Kildekoden til modellene ligger åpent tilgjengelig for alle på våre [Github-side](https://github.com/Informasjonsforvaltning). Hvordan vi har brukt Archi og en enkel oppskrift på hvordan ta dette i bruk vil du finne under de respektive arkitektur-modellene.
Det finnes også en en html-versjon av modellene. Linken til disse vil du finne på sidene under.

## API-first
Vi forsøker å utvikle våre komponenter etter “API”-first metodikken. Vi har derfor valgt å spesifisere [våre API](https://data.norge.no/dataservices?orgPath=%2FSTAT%2F972417858%2F991825827) etter OpenAPI Specification v 3.

## Åpen kildekode
Kildekoden til løsningen ligger åpent tilgjengelig på [Github](https://github.com/Informasjonsforvaltning).
All kildekode har en åpen lisens [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
