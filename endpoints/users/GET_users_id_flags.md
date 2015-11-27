# GET /users/#{id}/flags     
***
`/users/#{id}/flags`

### Description
***
Only available for the authenticated user, this call returns the user's chosen settings.

### Parameters
***

|header| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**id**|the user id to retrieve information from|integer|x||




### Response
***


200 and confirmation message


[Errors](../../resources/errors.md#files)

### Examples
***

`https://api.eyeem.com/v2/users/me/flags`





