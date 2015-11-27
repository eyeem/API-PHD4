# GET /search    
***
`/search`

### Description
***
Retrieves an array containing a users and an albums dictionary.

### Parameters
***

|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**q**|the keyword to search|string|x||
|**includeAlbums**| whether to include results in the albums dictionary|boolean||0|
|**includeUsers**|whether to include results in the users dictionary|boolean||0|
|**includeHidden**|include photos flagged as hidden|boolean||false|
|**includeBlacklisted**|include photos flagged as blacklisted|boolean||false|
|**autocomplete**|(works on albums only) boosts names starting with the provided keyword|boolean||true|
|**skipStopwords**|block queries based on a stopWord list|boolean||true|
|**limit**|num of items to return|integer||10|
|**offset**|(offset of items to start at|integer||0|

The `autocomplete` parameter can be used to disable the autocompletion boost on album names. With this paramter set to `false`, close matches rank higher then matches that only start with the provided keyword.

### Response
***

200 and an array containing a users dictionary and an albums dictionary.
