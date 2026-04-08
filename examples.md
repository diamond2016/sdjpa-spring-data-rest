## Examples
we want to follow this conventions for apis:
https://sfg-beer-works.github.io/brewery-api/#tag/Beer-Service/operation/listBeers

##  get - /beers
request: curl -X GET -H 'Accept: application/json' -H 'Content-Type: application/json' http://localhost:8080/api/v1/beers

response (default is through a property named "_embedded" that contains the list of beers), see also links below:
```json
{
  "_embedded" : {
    "beers" : [ {
      "beerName" : "Mango Bobs",
      "beerStyle" : "ALE",
      "upc" : "0631234200036",
      "quantityOnHand" : 95,
      "price" : 84.12,
      "createdDate" : "2026-04-08T08:54:40.648+00:00",
      "lastModifiedDate" : "2026-04-08T08:54:40.648+00:00",
      "_links" : {
        "self" : {
          "href" : "http://localhost:8080/api/v1/beers/46f01489-63bd-4c1b-8d0b-3389aabf4890"
        },
        "beer" : {
          "href" : "http://localhost:8080/api/v1/beers/46f01489-63bd-4c1b-8d0b-3389aabf4890"
        }
      }
    }, {
      "beerName" : "Galaxy Cat",
      "beerStyle" : "PALE_ALE",
      "upc" : "9122089364369",
      "quantityOnHand" : 1782,
      "price" : 45.36,
      "createdDate" : "2026-04-08T08:54:40.663+00:00",
      "lastModifiedDate" : "2026-04-08T08:54:40.663+00:00",
      "_links" : {
        "self" : {
          "href" : "http://localhost:8080/api/v1/beers/c13dbd67-9427-47ef-93da-2c58355b94a0"
        },
        "beer" : {
          "href" : "http://localhost:8080/api/v1/beers/c13dbd67-9427-47ef-93da-2c58355b94a0"
        }
      }
    },
    ...
    ]
  },
...
  "_links": {
    "first": {
      "href": "http://localhost:8080/api/v1/beers?page=0&size=20"
    },
    "self": {
      "href": "http://localhost:8080/api/v1/beers?page=0&size=20"
    },
    "next": {
      "href": "http://localhost:8080/api/v1/beers?page=1&size=20"
    },
    "last": {
      "href": "http://localhost:8080/api/v1/beers?page=1&size=20"
    },
    "profile": {
      "href": "http://localhost:8080/api/v1/profile/beers"
    },
    "search": {
      "href": "http://localhost:8080/api/v1/beers/search"
    }
  },
  "page": {
    "size": 20,
    "totalElements": 30,
    "totalPages": 2,
    "number": 0
  }
```

## get - /beers/{id}
request: curl -X GET -H 'Accept: application/json' -H 'Content-Type: application/json' http://localhost:8080/api/v1/beers/46f01489-63bd-4c1b-8d0b-3389aabf4890

response:
```json
{{
  "beerName" : "Mango Bobs",
  "beerStyle" : "ALE",
  "upc" : "0631234200036",
  "quantityOnHand" : 95,
  "price" : 84.12,
  "createdDate" : "2026-04-08T08:54:40.648+00:00",
  "lastModifiedDate" : "2026-04-08T08:54:40.648+00:00",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/api/v1/beers/46f01489-63bd-4c1b-8d0b-3389aabf4890"
    },
    "beer" : {
      "href" : "http://localhost:8080/api/v1/beers/46f01489-63bd-4c1b-8d0b-3389aabf4890"
    }
  }
}
```