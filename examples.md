## Examples
we want to follow this conventions for apis:
https://sfg-beer-works.github.io/brewery-api/#tag/Beer-Service/operation/listBeers

##  get - /beers
request: curl -X GET -H 'Accept: application/json' -H 'Content-Type: application/json' http://localhost:8080/api/v1/beer

response (default is through a property named "_embedded" that contains the list of beers), see also links below:
```json
{
  "_embedded" : {
    "beer" : [ {
      "beerName" : "Mango Bobs",
      "beerStyle" : "ALE",
      "upc" : "0631234200036",
      "quantityOnHand" : 3130,
      "price" : 75.05,
      "createdDate" : "2026-04-08T12:42:38.600+00:00",
      "lastModifiedDate" : "2026-04-08T12:42:38.600+00:00",
      "_links" : {
        "self" : {
          "href" : "http://localhost:8080/api/v1/beer/897cc999-0777-4fda-aede-7b34ec285905"
        },
        "beer" : {
          "href" : "http://localhost:8080/api/v1/beer/897cc999-0777-4fda-aede-7b34ec285905"
        }
      }
    }, {
      "beerName" : "Galaxy Cat",
      "beerStyle" : "PALE_ALE",
      "upc" : "9122089364369",
      "quantityOnHand" : 3153,
      "price" : 11.18,
      "createdDate" : "2026-04-08T12:42:38.621+00:00",
      "lastModifiedDate" : "2026-04-08T12:42:38.621+00:00",
      "_links" : {
        "self" : {
          "href" : "http://localhost:8080/api/v1/beer/7ae40008-d3ab-492e-95c2-a0d14dcff81f"
        },
        "beer" : {
          "href" : "http://localhost:8080/api/v1/beer/7ae40008-d3ab-492e-95c2-a0d14dcff81f"
        }
      }
    }, 
...
  "_links": {
    "first": {
      "href": "http://localhost:8080/api/v1/beer?page=0&size=20"
    },
    "self": {
      "href": "http://localhost:8080/api/v1/beer?page=0&size=20"
    },
    "next": {
      "href": "http://localhost:8080/api/v1/beer?page=1&size=20"
    },
    "last": {
      "href": "http://localhost:8080/api/v1/beer?page=1&size=20"
    },
    "profile": {
      "href": "http://localhost:8080/api/v1/profile/beers"
    },
    "search": {
      "href": "http://localhost:8080/api/v1/beer/search"
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