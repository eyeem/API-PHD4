# GET /search/suggestions/cities
***
`/search/suggestions/cities`

### Description
***
This endpoint provides a list of city suggestions for an input query. More precisely, the suggestions are cities and districts that are completion of the provided query. Note that the query can also contain a country in the following format: city, country. The suggestions are sorted by the number of albums for that city (i.e., by the `docCount` field stored in the index).

### Parameters
***

|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**q**|the text to search|string|true||
|**limit**|maximum number of suggestions returned|int|false|10|
|**offset**|position offset from the first result|int|false|0|

### Response
200 and an array named `suggestions` containing the requested suggestions.

The `suggestions` field contains a `location` array. Each object in the array contains 4 fields: `id` (id of the city), `city` (the city  name), `country` (the country of that city), and `text` (the city and the country separated by a comma).

Below is an example request and the corresponding response:

`GET https://api.eyeem.com/api/v2/search/suggestions/cities?q=berlin&limit=5`
````json
{
  "suggestions": {
    "locations": [
      {
        "id": 17,
        "city": "Berlin",
        "country": "Germany",
        "text": "Berlin, Germany"
      },
      {
        "id": 368520,
        "city": "Berlin Wilmersdorf",
        "country": "Germany",
        "text": "Berlin Wilmersdorf, Germany"
      },
      {
        "id": 380472,
        "city": "Berlin Köpenick",
        "country": "Germany",
        "text": "Berlin Köpenick, Germany"
      },
      {
        "id": 393960,
        "city": "Berlin Spandau",
        "country": "Germany",
        "text": "Berlin Spandau, Germany"
      },
      {
        "id": 394951,
        "city": "Berlin Steglitz Zehlendorf",
        "country": "Germany",
        "text": "Berlin Steglitz Zehlendorf, Germany"
      }
    ]
  }
}
````
