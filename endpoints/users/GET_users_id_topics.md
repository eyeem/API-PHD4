# GET /users/#{id}/topics    
***
`/users/#{id}/topics`

### Description
***
Get a list of topics the user has contributed to (the topics correlate to tag albums).

### Parameters
***

|header| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**id**|the user id to retrieve information from|integer|x||
|**parameter**| **description**| **type** |**required?** |**default**|
|**limit**|num of topics to return|integer||20|
|**offset**|offset of topics to start at|integer||0|


### Response
***