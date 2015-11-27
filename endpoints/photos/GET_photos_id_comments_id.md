# GET /photos/#{id}/comments/#{comment_id}   
***
`/photos/#{id}/comments/#{comment_id} `

### Description
***
Retrieves a specific comment on a photo.

### Parameters
***

|header| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**id**|The id of the photo we want retrieve information about.|integer|x||
|**comment_id**|The id of the comment we want to retrieve.|integer|x||


### Response
***


200 and a comment object

[Errors](../../resources/errors.md#files)