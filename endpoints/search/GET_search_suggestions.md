# GET /search/suggestions
***
`/search/suggestions`

### Description
***
Provides a list of suggestions related to a certain input query.

This same endpoint allows to retrieve suggestions of two different kinds:
* __album suggestions__ provide a list of album or users that match the provided query, by executing a search on the album/user indexes; because of their implementation, these suggestions are rather slow and are deprecated.
* __FST suggesions__ provide a list of keywords, users and locations that complete the provided query. They are implemented using Elasticsearch's completion suggester and the average reponse time at the backend level is around 70ms.

### Parameters
***

|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**q**|the text to search|string|true||
|**topicId**|(album only) array of topic ids already selected by the user|int|||
|**citycountryId**|(album only) city id already selected by the user|int|||
|**venueId**|(album only) venue id already selected by the user|int|||
|**userId**|(album only) user id already selected by the user|int|||
|**IncludeHidden**|whether to show or hide hidden entities|bool||false|
|**IncludeBlacklisted**|whether to show or hide blacklisted entities|bool||false|
|**type**|defines which type of suggestions is returned. Possible options are `album`, `keyword`, `fst`|string||'album'|

### Response
200 and an array named `suggestions` containing the requested suggestions.

#### Album suggestions (default)
`https://www.eyeem.com/api/v2/search/suggestions?type=album&q=a`

Each entry of the array contains a `type` field. In case an entry is of type `multi`, its `elements` field contains the list of entities to be displayed. In any other case, the entry is one self-contained suggestion.

#### FST suggestions

The `suggestions` field contains three objects: `keywords`, `location`, `users`. Each field contains a list of objects including the specific fields for that entity type and the `docCount` field, containing the number of photos that a search with a corresponding query would return.


`GET https://www.eyeem.com/api/v2/search/suggestions?type=fst&q=a`
````json
{
   "suggestions":{
      "keywords":[
         {
            "text":"architecture",
            "docCount":150635
         },
         {
            "text":"autumn",
            "docCount":44023
         },
         {
            "text":"abstract",
            "docCount":22197
         },
         {
            "text":"amazing",
            "docCount":19769
         },
         {
            "text":"artwork",
            "docCount":14136
         }
      ],
      "locations":[
         {
            "text":"Amsterdam, NL",
            "id":"629",
            "docCount":15463
         },
         {
            "text":"Ad Damm\u0101m, SA",
            "id":"2512",
            "docCount":10355
         }
      ],
      "users":[
         {
            "nickname":"ADNANBEKAR",
            "fullname":"ADNAN BEKAR",
            "id":3281875,
            "docCount":19073
         },
         {
            "nickname":"angelamarcospenalver",
            "fullname":"Angela Marcos Pe\u00f1alver",
            "id":2560644,
            "docCount":6717
         }
      ]
   }
}
````
