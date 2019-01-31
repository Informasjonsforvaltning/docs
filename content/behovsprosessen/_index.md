---
title: Behovsprosessen
---

Vår behovsprosess er implementert som et GitHub-prosjekt og er <a href="https://github.com/orgs/Informasjonsforvaltning/projects/3" target="_blank">åpent tilgjengelig</a>. Behovsprosessen starter ved at det er registrert et issue på en av våre løsninger eller på vårt dedikerte <a href="https://github.com/Informasjonsforvaltning/behov" target="_blank">behovsprosjekt</a>.

Den har følgende steg:
## Avklare behov
*Kriteria: Issuet skal vere identifisert som et potensielt behov.*

| Roller | Aktivitet | Verktøy |
| ------ | --------- | ------- |
| Gevinstansvarlig | Opprette epos og utarbeide enkel gevinstanalyse | GitHub |
| Funksjonell arkitekt | Opprette brukerhistorier | GitHub |
## Analysere behov
*Kriteria:Behovet skal vere formulert som et epos og ha en enkel gevinstanalyse.*

| Roller | Aktivitet | Verktøy |
| ------ | --------- | ------- |
| Funksjonell arkitekt | Detaljere epos og brukerhistorier som operasjonaliserer eposet | GitHub |
| Løsningsarkitekt | Dokumentere relevante kvalitetskrav | |
| Interaksjonsdesigner | Lage trådskisser der dette er relevant | |
## Beskrive design og løsningsarkitektur
*Kriteria: Eposet skal ha ei eller flere brukerhistorier knytta til seg*

| Roller | Aktivitet | Verktøy |
| ------ | --------- | ------- |
| Løsningsarkitekt | Utarbeide løsningsarkitektur | [Archi](https://github.com/Informasjonsforvaltning/SA_Informasjonsforvaltning) |
| Designer | Utarbeide design basert på trådskisser | |
| Senior utvikler | Utarbeide features i [Gherkin](https://docs.cucumber.io/gherkin/reference/)| GitHub |
## Klar til konstruksjon
*Kritieria: Brukerhistorien skal ha et design (der det er relevant), en løsningsarkitektur og et sett av features. Brukerhistoriene skal også prioriteres*

| Roller | Aktivitet | Verktøy |
| ------ | --------- | ------- |
| Produkteier | Prioritere brukerhistorier | GitHub |
| Scrumleder | Opprette brukerhistorien i utviklingsprosjekt | GitHub |
| Seniorutvikler | Dele brukerhistorien opp i oppgaver | GitHub |
___
*Her vil brukerhistorien bli duplisert over i det relevante utviklingsprosjektet, som oppretter sine brukerhistorier etter behov. Disse skal referere til den opprinnelige brukerhistorien i behovsprosjektet. Utviklingsteamet vil også legge brukerhistorien ut i sine prosjekter med tilhørende milepæler.*
___
## Klar til akseptansetest
*Kriteria: Utviklingsteamet har levert funksjonalitet til staging-miljø som realiserer brukerhistorien.*

| Roller | Aktivitet | Verktøy |
| ------ | --------- | ------- |
| Produkteier | | |
| Funksjonell arkitekt | | |
| Løsningsarkitekt | |
