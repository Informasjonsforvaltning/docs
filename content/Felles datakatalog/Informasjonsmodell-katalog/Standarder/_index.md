---
title: Standarder
weight: 1
---
Informasjonsmodell-katatalogen representerer modeller på to måter:

## Struktur
Dette er en fritekstlig representasjon av modellen med navn på elementet og elementets type.

## JSON Schema
Dette er en representasjon av modellen i form av <a href="https://json-schema.org/" target="_blank">JSON Schema</a>. Vi støtter pr i dag draft-06 av spesifikasjonen. For eksempel slik:
```
{
  "$schema": "http://json-schema.org/draft-06/schema#",
  "$id": "https://fellesdatakatalog.digdir.no/informationmodels/c207ad40-cf59-47e6-b7a8-35d6c4692067/schema",
  "definitions": {
    "QueryResponse": {
      "type": "object",
      "properties": {
        "aggregations": {
          "$ref": "#/definitions/Aggregation"
        },
        "hits": {
          "type": "array",
          "items": {
            "$ref": "#/definitions/ConceptDocument"
          }
        },
        "total": {
          "type": "integer",
          "format": "int64"
        }
      }
    },
    "Aggregation": {
      "type": "object"
    },
    "ConceptDocument": {
      "type": "object"
    },
    "ErrorMessage": {
      "type": "object"
    }
  }
}
```
