---
title: Hvordan publisere begreper i begrepskatalogen
weight: 4
---
Her følger en kort beskrivelse av hvordan man kan publisere begreper i Felles datakatalog.

## Registrere begreper i Begrepskatalog GUI
I [registreringsløsningen](https://registrering.fellesdatakatalog.digdir.no) vår kan du registrere begreper og velge å publisere de slik at informasjonen blir tilgjengelig i portalløsningen av Felles datakatalog https://data.norge.no.

### Importere Begreper
Virksomheter som har utarbeidet en strukturert oversikt over noen av sine begreper, for eksempel i et regneark eller tabell, kan overføre disse til registreringsløsningen i Felles datakatalog gjennom import av en CSV- eller JSON fil.

#### Hvordan Importere begreper fra CSV format? 
For at importen til registreringsløsningen skal fungere må begrepene og beskrivelsene følge en struktur som er nærmere beskrevet i denne [malen](https://github.com/Informasjonsforvaltning/fdk-testdata/raw/master/testdata/concept_sample.xlsx)

Noen av kolonnene, for eksempel _Bruksområde_ har støtte for flere verdier. For å legge inn flere forekomster legger du til en ekstra kolonne med samme navn på første linje (overskrift).

Enkelte felter har også støtte for flere språk og målformer. Den nåværende importløsningen støtter norsk bokmål (nb), nynorsk (nn) og engelsk (en). Hvis språk og målform ikke er oppgitt vil denne automatisk bli satt til bokmål under importen.

Legg til eller kopier inn termer og tilhørende informasjon ved å sette inn flere rader inntil listen du ønsker å importere til Registreringsløsningen er komplett.

##### Eksempel:
I tabellen nedenfor er kolonne a og b formattert for norsk bokmål, og kolonne c og d for engelsk.

| anbefaltTerm:nb | tillattTerm:nb | anbefaltTerm:en | tillattTerm:en | frarådetTerm:nb | definisjon:nb | 
| --- | --- | --- | --- | --- | --- |
| test eksempel	| eksempeltest | test example | example test | illustrasjonstest | Dette er en definisjon på et eksempel |

Kolonner som ikke gjenkjennes under importen vil bli ignorert, så test gjerne med et par begreper først og kontroller at disse blir korrekt importert i registreringsløsningen. Selve rekkefølgen på kolonnene har ikke noe å si for importen av begreper.


##### Om innholdet i feltene
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


##### Lagring
Når du har fylt tabellen med innhold i henhold til malen (riktig formattering) må du huske å eksportere den som en CSV-fil med semikolon separering og UTF-8 koding. 

Eksempel med utgangspunkt i Excel for Microsoft 365:

* 1 - Trykk på 'Export'
* 2 - Trykk på 'Change File Type'
* 3 - Velg 'CSV (comma delimited)'
* 4 - Trykk på 'Save as'
* 5 - Velg 'CSV UTF-8 (comma delimited)' under 'Save as type'

![Eksportering til csv med excel|1673x717,50%](Export_csv.png)
![Eksportering til csv med excel, valg av filformat|1179x649,50%](Export_csv2.png)

Du er nå klar for å importere CSV filen i registreringsløsningen.


##### Eksempel på CSV-fil:
```
anbefaltTerm:nb;tillattTerm:nb;anbefaltTerm:en;tillattTerm:en;frarådetTerm:nb;definisjon:nb
test eksempel;eksempeltest;Test example;example test;illustrasjonstest;Dette er en definisjon på et eksempel
```


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
