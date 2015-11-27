# GET /albums/#{id}/favoriters 
***
`/albums/#{id}/favoriters`

### Description
***
Retrieves an array of the users who favorited the album.

### Parameters
***

|header| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**id**| the id of the album|integer|x||
|**parameter**| **description**| **type** |**required?** |**default**|
|**limit**|num of favoriters to return|integer||20|
|**offset**|offset of favoriters to start at|integer||0|
|**onlyId**|returns a json array userIds (ignoring pagination) containing just the ids|boolean|no|false|



### Response
***

200 and and a dictionary containing limit, offset, total and an array of favoriters (users)
