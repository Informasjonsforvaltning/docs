---
title: Åpen behovsprosess
weight: 2
---

Vår behovsprosess er implementert som et GitHub-prosjekt og er <a href="https://github.com/orgs/Informasjonsforvaltning/projects/3" target="_blank">åpent tilgjengelig</a>. Behovsprosessen starter ved at det er registrert et issue på en av våre løsninger eller på vårt dedikerte <a href="https://github.com/Informasjonsforvaltning/behov/issues" target="_blank">behovsprosjekt</a>.

Behovsprosessen har følgende steg:

## Avklare behov
*Kriteria: Issuet skal vere identifisert som et potensielt behov.*

| Ansvarlig rolle | Aktivitet | Verktøy |
| --------------- | --------- | ------- |
| Gevinstansvarlig | Opprette epos og utarbeide enkel gevinstanalyse | GitHub |
| Funksjonell arkitekt | Opprette brukerhistorier | GitHub |

## Analysere behov
*Kriteria: Behovet skal vere formulert som et epos og ha en enkel gevinstanalyse.*

| Ansvarlig rolle | Aktivitet | Verktøy |
| --------------- | --------- | ------- |
| Funksjonell arkitekt | Detaljere epos og brukerhistorier som operasjonaliserer eposet | GitHub |
| Løsningsarkitekt | Dokumentere relevante kvalitetskrav | |
| Interaksjonsdesigner | Lage trådskisser der dette er relevant | |

## Beskrive design og løsningsarkitektur
*Kriteria: Eposet skal ha ei eller flere brukerhistorier knytta til seg.*

| Ansvarlig rolle | Aktivitet | Verktøy |
| --------------- | --------- | ------- |
| Løsningsarkitekt | Utarbeide løsningsarkitektur | <a href="https://github.com/Informasjonsforvaltning/SA_Informasjonsforvaltning" target="_blank">Archi</a> |
| Designer | Utarbeide design basert på trådskisser | |
| Testleder | Utarbeide akseptansekriteria som features i <a href="https://docs.cucumber.io/gherkin/reference/" target="_blank">Gherkin</a> | GitHub |
| Senior utvikler | Utarbeide scenarier i features | GitHub |

## Klar til konstruksjon
*Kritieria: Brukerhistorien skal ha et design (der det er relevant) og en løsningsarkitektur. Akseptansekriteria skal være dokumentert som et sett av features.*

| Ansvarlig rolle | Aktivitet | Verktøy |
| --------------- | --------- | ------- |
| Produkteier | Prioritere brukerhistorier | GitHub |
| Scrumleder | Opprette brukerhistorien i utviklingsprosjekt | GitHub |
| Seniorutvikler | Dele brukerhistorien opp i oppgaver | GitHub |
___
## I konstruksjon
*Kritieria: Brukerhistorien er prioritert og opprettet i utviklingsprosjekt.*

*Her vil brukerhistorien bli duplisert over i det relevante utviklingsprosjektet, som oppretter sine brukerhistorier etter behov. Disse skal referere til den opprinnelige brukerhistorien i behovsprosjektet. Utviklingsteamet vil også legge brukerhistorien ut i sine prosjekter med tilhørende milepæler.*
___

## Klar til akseptansetest
*Kriteria: Utviklingsteamet har levert funksjonalitet til staging-miljø som realiserer brukerhistorien.*

| Ansvarlig rolle | Aktivitet | Verktøy |
| --------------- | --------- | ------- |
| Funksjonell arkitekt | Godkjenne levert funksjonalitet | |
| Løsningsarkitekt | Godkjenne levert kvalitet |
| Produkteier | Akseptere levert funksjonalitet  | |

## Utført
*Kriteria: Funksjonalitet og kvalitet er godkjent i akseptansetest og issue er "closed". Eller det er bestemt at behovet ikke skal taes videre i behovsprosessen.*
Alle issues som blir lukka vil automatisk havne i denne kolonnen.
