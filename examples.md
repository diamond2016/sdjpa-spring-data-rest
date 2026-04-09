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

##  post - create - /beers 
request:
```bash 
curl -X POST -H 'Accept: application/json' -H 'Content-Type: application/json'  -d '{"beerName":"Galaxy Cat 2","beerStyle":"PALE_ALE","upc":"US0000000000","quantityOnHand":200,"price":12.34}' http://localhost:8080/api/v1/beer
```

response: 
```json
{
  "beerName" : "Galaxy Cat 2",
  "beerStyle" : "PALE_ALE",
  "upc" : "US0000000000",
  "quantityOnHand" : 200,
  "price" : 12.34,
  "createdDate" : "2026-04-09T14:59:12.205+00:00",
  "lastModifiedDate" : "2026-04-09T14:59:12.205+00:00",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4"
    },
    "beer" : {
      "href" : "http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4"
    }
  }
  ```

  ##  put - update - /beers/{id}
  request:
  ```bash
  curl -X PUT -H 'Accept: application/json' -H 'Content-Type: application/json'  -d '{"beerName":"Galaxy Cat 2","beerStyle":"PALE_ALE","upc":"US0000000000","quantityOnHand":300,"price":12.34}' http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4
  ``` 
  response: 
  ```json
  {
    "beerName" : "Galaxy Cat 2",
    "beerStyle" : "PALE_ALE",
    "upc" : "US0000000000",
    "quantityOnHand" : 300,
    "price" : 12.34,
    "createdDate" : "2026-04-09T14:59:12.205+00:00",
    "lastModifiedDate" : "2026-04-09T15:01:45.123+00:00",
    "_links" : {
      "self" : {
        "href" : "http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4"
      },
      "beer" : {
        "href" : "http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4"
      }
    }
  }
  ```

  ##  put - delete - /beers/{id}
  request:
  ```bash
  curl -X DELETE -H 'Accept: application/json' -H 'Content-Type: application/json' http://localhost:8080/api/v1/beer/1317b23e-a423-4b26-ba1b-3104629312a4
  ```
  response:  + body with deleted beer
  second time another get - 404 not found

## search - /beers/search/findByUpc?upc={upc}
request: 
```bash
curl -X GET -H 'Accept: application/json' -H 'Content-Type: application/json'
    http://localhost:8080/api/v1/beer/search/findByUpc?upc=9122089364369
```
response:
```json
{
    "beerName": "Galaxy Cat",
    "beerStyle": "PALE_ALE",
    "upc": "9122089364369",
    "quantityOnHand": 1120,
    "price": 0.89,
    "createdDate": "2026-04-09T14:56:54.269+00:00",
    "lastModifiedDate": "2026-04-09T14:56:54.269+00:00",
    "_links": {
        "self": {
            "href": "http://localhost:8080/api/v1/beer/aea7c9b1-e86a-4ed7-be56-20dba130b9fc"
        },
        "beer": {
            "href": "http://localhost:8080/api/v1/beer/aea7c9b1-e86a-4ed7-be56-20dba130b9fc"
        }
    }
}
```

