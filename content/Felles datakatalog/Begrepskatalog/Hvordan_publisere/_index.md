---
title: Hvordan publisere begreper i begrepskatalogen
weight: 4
---
Her følger en kort beskrivelse av hvordan man kan publisere begreper i Felles datakatalog.

## Registrere begreper i Begrepskatalog GUI
I [registreringsløsningen](https://registrering.fellesdatakatalog.digdir.no) vår kan du registrere begreper og publisere de ut til portalløsningen https://data.norge.no.

### Importere Begreper
I denne forbindelsen har vi en funksjonalitet for å importere ferdigbeskrevet begreper fra CSV- og JSON-formater

#### Hvordan Importere begreper fra CSV format? 
Tabellen består av en rekke kolonne-overskrifter. For at dataene skal leses riktig må overskriftene og dataene være formattert riktig. Enkelte kolonner støtter flere verdier, f.eks bruksområde. For å legge inn flere forekomster av noe, bare legg til en ekstra kolonne med samme navn på første linje(overskrift).

Enkelte felter støtter også språk og målform. Støttede språk og målformer er for øyeblikket engelsk(en), nynorsk(nn) og norsk bokmål(nb). Om ikke språk og måform er definert så settes bokmål som default.
Se SKOS terminologi i øverste rad, og verdien i radene under. Legg til flere begreper under.

| anbefaltTerm:nb | tillattTerm:nb | anbefaltTerm:en | tillattTerm:en | frarådetTerm:nb | definisjon:nb | 
| --- | --- | --- | --- | --- | --- |
| test eksempel	| eksempeltest | test example | example test | illustrasjonstest | Dette er en definisjon på et eksempel |

Her er ett eksempel på bruk av bruksområde hvor kolonne a og b er formattert for norsk bokmål (norsk bokmål om ikke annet er oppgitt), og kolonne C og D er på engelsk. Rekkefølgen på kolonnene har ikke noe å si for importering av begreper.

Kolonner som ikke gjenkjennes vil bli ignorert, så det kan være lurt å teste først med et par begreper og kontrollere at disse ble importert korrekt i registreringsløsningen.

Når formatteringen av tabellen med dine data er ferdig husk å eksportere til CSV separert med semikolon og UTF-8 encoding, og deretter importer CSV filen i registreringsløsningen.

CSV filen skal se slik ut:
```
anbefaltTerm:nb;tillattTerm:nb;anbefaltTerm:en;tillattTerm:en;frarådetTerm:nb;definisjon:nb
test eksempel;eksempeltest;Test example;example test;illustrasjonstest;Dette er en definisjon på et eksempel
```

[Last ned eksempelfil med alle felter](https://github.com/Informasjonsforvaltning/fdk-testdata/raw/master/testdata/concept_sample.xlsx)

Dette er en excelfil som kan manipuleres ved å endre innholdet i feltene. Man kan legge til flere begreper ved å legge til nye rader.
Husk å eksportere som CSV separert med semikolon og UTF-8 encoding.

#### Veiledning for eksport til UTF-8:
![Eksport til csv med excel](Export_csv.png)
![Eksport til csv med excel - velg filformat](Export_csv2.png)

* 1 - Trykk på 'Export'
* 2 - Trykk på 'Change File Type'
* 3 - Velg 'CSV (comma delimited)'
* 4 - Trykk på 'Save as'
* 5 - Velg 'CSV UTF-8 (comma delimited)' under 'Save as type'


#### Gyldige felter
| Felt | Kommentar | Eksempel |
| --- | --- | --- |
| anbefaltTerm | Flere språk og målformer, kun en kolonne pr språk og målform. | |
| tillattTerm | Flere språk og målformer, ubegrenset antall kolonner pr målform (kan ha flere tillatte termer). | |
| frarådetTerm | Flere språk og målformer, ubegrenset antall kolonner pr målform (kan ha flere frarådede termer). | |
| definisjon | Flere språk og målformer, kun en kolonne pr språk og målform. | |
| forholdtilkilde | må være en av: «egendefinert», «basertPaaKilde» eller «sitatFraKilde» | |
| kilde | Formatteres med tekst beskrivelse og gyldig uri til kilde separert med tegnet \|. | «brønnøysund\|https://www.brreg.no/» |
| merknad | Flere språk og målformer, kun en kolonne pr språk og målform. | |
| eksempel | Flere språk og målformer, kun en kolonne pr språk og målform. | |
| fagområde | Flere språk og målformer, kun en kolonne pr språk og målform. | |
| bruksområde | Flere språk og målformer, ubegrenset antall kolonner pr målform (kan ha flere bruksområder termer). | |
| omfang_uri | Kun en kolonne. | |
| omfangtekst | Kun en kolonne. | |
| kontaktpunkt_epost | Kun en kolonne. Rader må inneholde gyldig epostadresse. | |
| kontaktpunkt_telefon | Kun en kolonne. | |
| gyldigfom | Fra og med dato for perioden hvor begrepet er gyldig. Kun en kolonne. Dato formattert med (åååå-mm-dd) år, måned, dag. | 2020-01-31 |
| gyldigtom | Til og med dato for perioden hvor begrepet er gyldig. Kun en kolonne. Dato formattert med (åååå-mm-dd) år, måned, dag. | 2020-12-01 |
| seogså | NB! Dette feltet kan ikke brukes til eksterne referanser utenfor begrepskatalogen. Det anbefales sterkt å sette dette etter begrepet er registrert inn. Kun en kolonne støttes og rader må inneholde en gyldig uri som peker til eksisterende begrep i begrepskatalogen. | |


#### Hvordan Importere begreper fra JSON format? 
Opprett en JSON fil med 1 eller flere begreper på formatet under:
```
[
  {
    "anbefaltTerm": {
      "navn": {
        "nb": "1demoterm1811",
	"en":"Test English term"
      }
    },
    "tillattTerm": {
      "nb": [
        "Tillatt term"
      ]
    },
    "frarådetTerm": {
      "nb": [
        "Frarådet term"
      ]
    },
    "definisjon": {
      "tekst": {
        "nb": "definisjon"
      }
    },
    "kildebeskrivelse": {
      "forholdTilKilde": "egendefinert",
      "kilde": []
    },
    "merknad": {
      "nb": "merknad"
    },
    "eksempel": {
      "nb": "bruk av begrepet: Eksempel"
    },
    "fagområde": {
      "nb": "bruk av begrepet: Fagområde"
    },
    "bruksområde": {
      "nb": [
        "bruk av begrepet: bruksområde(r)"
      ]
    },
    "omfang": {
      "uri": "lenketilomfangno",
      "tekst": "bruk av begrepet: Omfang: Tittel på omfang"
    },
    "kontaktpunkt": {
      "harEpost": "e-post@epost.no",
      "harTelefon": "47474747"
    },
    "gyldigFom": "2019-12-31",
    "gyldigTom": "2020-12-30",
    "endringslogelement": {
      "brukerId": "03096000854",
      "endringstidspunkt": "2020-10-14T12:54:52.264+02:00"
    },
    "seOgså": [
      "http://begrepskatalogen/begrep/98da4336-dff2-11e7-a0fd-005056821322",
      "http://begrepskatalogen/begrep/98da4336-dff2-11e7-a0fd-005056821322"
    ]
  },
  {
    "anbefaltTerm": {
      "navn": {
        "nb": "2demoterm1811"
      }
    },
    "tillattTerm": {
      "nb": [
        "Tillatt term"
      ]
    },
    "frarådetTerm": {
      "nb": [
        "Frarådet term"
      ]
    },
    "definisjon": {
      "tekst": {
        "nb": "definisjon"
      }
    },
    "kildebeskrivelse": {
      "forholdTilKilde": "egendefinert",
      "kilde": []
    },
    "merknad": {
      "nb": "merknad"
    },
    "eksempel": {
      "nb": "bruk av begrepet: Eksempel"
    },
    "fagområde": {
      "nb": "bruk av begrepet: Fagområde"
    },
    "bruksområde": {
      "nb": [
        "bruk av begrepet: bruksområde(r)"
      ]
    },
    "omfang": {
      "uri": "http://lenketilomfang.no",
      "tekst": "bruk av begrepet: Omfang: Tittel på omfang"
    },
    "kontaktpunkt": {
      "harEpost": "e-post@epost.no",
      "harTelefon": "47474747"
    },
    "gyldigFom": "2019-12-31",
    "gyldigTom": "2020-12-30",
    "endringslogelement": {
      "brukerId": "03096000854",
      "endringstidspunkt": "2020-10-14T12:54:52.264+02:00"
    },
    "seOgså": [
      "http://begrepskatalogen/begrep/98da4336-dff2-11e7-a0fd-005056821322",
      "http://begrepskatalogen/begrep/98da4336-dff2-11e7-a0fd-005056821322"
    ]
  }
]
```


## Publisere en begrepssamling via vår høsteløsning
For å publisere en begrepssamling via vår høsteløsning må følgende gjøres:
1. Tilgjengeliggjøre begrepssamlingen som SKOS-AP-NO, og
2. Konfigurere FDKs høsteløsning
### Tilgjengeliggjøre begrepssamlingen som SKOS-AP-NO

### Konfigurere FDKs høsteløsning
