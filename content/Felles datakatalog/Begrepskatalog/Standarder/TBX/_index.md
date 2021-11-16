---
title: TermBase Exchange (TBX)
weight: 4
---
## Standard for tilgjengeliggjøring av begrep - TBX

ISO 30042 Systems to manage terminology, knowledge and content —TermBase eXchange (TBX):
Standarden definerer et rammeverk for hvordan (samlinger av) begrepsbeskrivelser skal kunne utveksles i maskinlesbare formater.
Spesifikasjonen i dette kapitlet utgjør definisjonen av en TBX-dialekt, kalt TBX-AP-No. Dialektnavnet TBX-AP-No skal oppgis i en TBX-fil for å være i samsvar med denne standarden: <tbx type="TBX-AP-No">.

Spesifikasjonen sier ikke hva som er obligatoriske felter, men hvordan et felt skal representeres i TBX når feltet brukes. Se Forvaltningsstandard for begrepsbeskrivelser hhv. TBX for hva som er obligatorisk.

For referanser fra et begrep til andre begreper, har vi valgt å bruke <xref>, også i tilfeller begreper som refereres til er i samme TBX-fil. Dette fordi Forvaltningsstandard for begrepsbeskrivelser krever at ethvert begrep skal ha en URI. I tabellen under er det også tatt med PID (persistent identifier) til definisjoner av datafelter og kodeverdier. Dette for å oppnå semantisk interoperabilitet med andre TBX-dialekter, ved at man gjennom unike PIDer refererer til samme definisjoner av datafelter og kodeverdier, selv om man bruker ulike termer i ulike TBX-dialekter. Vi bruker primært PIDer som finnes fra ISO (www.isocat.org/datcat/), supplert med definisjoner/PIDer fra andre offisielle kilder (bl.a. SKOSog Dublin Core).

Der det p.t. ikke finnes ferdige internasjonale definisjoner, er PID oppgitt med prefiks “skosno:”. Disse vil bli definert og publisert senere under vokab.norge.no/skosno#. PIDer er ikke nødvendig å oppgi i en TBX-fil, men brukes til å slå opp i definisjoner når man implementerer eller tolker en TBX-fil som er i samsvar med denne standarden.
