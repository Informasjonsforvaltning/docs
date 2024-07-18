---
title: Search
weight: 1
---

The service responsible for handling searches is [fdk-search-service](https://github.com/Informasjonsforvaltning/fdk-search-service), which is described by [this OpenAPI specification](https://raw.githubusercontent.com/Informasjonsforvaltning/fdk-search-service/main/openapi.yaml).

Production endpoint: <https://search.api.fellesdatakatalog.digdir.no/search>
Demo endpoint: <https://search.api.demo.fellesdatakatalog.digdir.no/search>
Staging endpoint: <https://search.api.staging.fellesdatakatalog.digdir.no/search>

Simple example using the staging endpoint:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test"}'
```

### Searchable fields

There are 3 searchable fields, they are `title`, `description` and `keyword`. The service will by default try to find matches for the query in all 3 fields, but it's possible to define which of the fields it should include in the search body.

Example where only hits from the description fields are included:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test", "fields": {"title":false,"description":true,"keyword":false}}'
```

#### Boosting

Hits from some fields will be prioritized over others, i.e. a matching hit from the title field will be prioritized over a hit from the description field.

| Field | Boost |
| ------ | ------ |
| title, full phrase match | 30 |
| title, partial match | 15 |
| keyword | 5 |
| description | 1 |

Take the title "Test search service" and the two queries "test service" and "search service". The first query will have 2 partial matches "test" and "service", with a combined search value of 15 + 15 = 30, the second query will have 3 matches where two are partial, "search" and "service", and one is a full phrase match, "search service", with a combined search value of 15 + 15 + 30 = 60.

### Specific resource types

Each resource type has it's own endpoint, the available endpoints are `/datasets`, `/data-services`, `/concepts`, `/information-models`, `/events` and `/services`

Example using the datasets endpoint:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search/datasets' -H 'Content-Type: application/json' -d '{"query":"test"}'
```

### Pagination

All search results will be paginated, it is possible to customize the size and page number with the pagination field in the search body.

Example using the pagination field, with current page set to number 5 and there are 10 hits per page:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test","pagination":{"size":10,"page":5}}'
```

### Filtering

It's possible to filter the search result, see SearchFilters in the [OpenAPI specification](https://raw.githubusercontent.com/Informasjonsforvaltning/fdk-search-service/main/openapi.yaml) for a list of all possible filters and what type of value they accept.

Example using the data theme filter:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test","filters":{"dataTheme":{"value":["ENVI"]}}}'
```

Example using the open data filter:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test","filters":{"openData":{"value":true}}}'
```

Example using the formats filter:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test","filters":{"formats":{"value":["MEDIA_TYPE application/json"]}}}'
```

#### Aggregations

Each search result will include aggregations of the query for possible filter values. There are always included a value for each filter, it's a list of the filter options represented in the total search result and a count of how many hits the filter option has.

Given that this search:
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test"}'
```
Has this as the aggregation in the result:
```
"aggregations":{"accessRights":[{"key":"PUBLIC","count":5},{"key":"RESTRICTED","count":16}]}
```

Then the next example would therefore have 5 hits in it's result, since the aggregation values shows that the query has 5 hits where the value for the access rights field is PUBLIC and 16 where the value is RESTRICTED.
```Shell
curl -X POST 'https://search.api.staging.fellesdatakatalog.digdir.no/search' -H 'Content-Type: application/json' -d '{"query":"test","filters":{"accessRights":{"value":"PUBLIC"}}}'
```
