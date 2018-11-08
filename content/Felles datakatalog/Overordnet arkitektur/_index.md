---
title: Overordnet arkitektur
---

Her følger en kort oversikt over den overordnede arkitekturen til våre komponenter. Nederst på denne siden finner du lenker til mer detaljerte beskrivelser.

### Om komponentene

* Felles Datakatalog Portal: grafisk brukergrensesnitt der publikum har generell tilgang til oversikt over innhold som er publisert av hver enkelt virksomhet. (også kalt “søkeløsningen”)
* Felles katalog: samling av kataloger som virksomheter har publisert. Denne komponenten tilbyr et maskin-til-maskin grensesnitt (API).  
* Registreringsløsning: En administrativt løsning der virksomheten der virksomheter administrerer sin katalog og høsteløsning fra eventuell virksomhetsintern informasjonsmodell-katalog
* Virksomhetsintern katalog: lokale kataloger som er installert hos den enkelte virksomhet og vedlikeholdes og driftes av virksomheten. Understøtter høsting.


Våre arkitekturmodeller er laget i henhold til Archimate-rammeverket med hjelp av verktøyet Archi. Kildekoden til modellene ligger åpent tilgjengelig for alle på [Github](
https://github.com/Informasjonsforvaltning/SA_Informasjonsforvaltning). Det finnes også en en [html-versjon av modellene](https://informasjonsforvaltning.github.io/SA_Informasjonsforvaltning) dersom du kun ønsker å se på dem.


Vi forsøker å utvikle våre komponenter etter “API”-first metodikken. Vi har valgt å spesifisere [våre API](https://github.com/brreg/openAPI) etter OpenAPI Specification v 3.

Åpen kildekode
Kildekoden til løsningen ligger åpent tilgjengelig på [Github](https://github.com/Informasjonsforvaltning/fdk)

All kildekode har en åpen lisens (Apache License 2.0)
