# GET /feed/follow

### Description

Retrieves a dedicated follow feed .

***Important***:
The follow feed *might* return less objects than requested. Meaning if you queried for limit=20 you might receive e.g. 18 elements, but you are not on the end of the feed yet - rely on the totals. This behaviour arises when photos are deleted after the feed has been generated.


### Parameters

| parameter       | description                                         |   type  | required? |                  default                 |
|-----------------|-----------------------------------------------------|:-------:|:---------:|:----------------------------------------:|
| **limit**       | max num of items to return (may return fewer items) | integer |           |                    20                    |
| **offset**      | offset of items to start at                         | integer |           |                     0                    |

### Headers

| header            |                   default                |
|-------------------|:----------------------------------------:|
| **X-Api-version** | `$v2DefaultVersion` in Eyeem\Api\Version |


### Example response

For `X-Api-version < 2.3.5`, the response will only contain items of type `photo` or type `album`
```
{
    "follow": {
        "offset": 0,
        "limit": 20,
        "total": 85,
        "items": [ 
            {
              "type": "photo",
              "photo": { ... }
            }, 
            {
                 "type": "album",
                 "album": { ... }
               }, ...
        
```

For `X-Api-version >= 2.3.5`, the response can contain also items of type `photoGroup` containing all photoIds of that group (group of photos by the same owner that were uploaded within a similar time period, currently: 1 hour) and a sample of (currently: 5) photos including all their metadata.

```
{
    "follow": {
        "offset": 0,
        "limit": 20,
        "total": 85,
        "items": [ 
            {
              "type": "photo",
              "photo": { ... }
            }, 
            {
                 "type": "photoGroup",
                 "photoGroup": { 
                    "sample": [
                                            {
                                                "id": 70715905,
                                                "file_id": "211b2130811c3692ba4e9091664cdfa65d870724-1439289623",
                                                "photoUrl": "http://cdn.eyeem.com/thumb/640/480/211b2130811c3692ba4e9091664cdfa65d870724-1439289623",
                                                //....
                                            }, 
                                            //... (a sample of the first (currently: 5) full photo objects 
                               ],
                    "photoIds": [
                                           70715905,
                                           70715904,
                                           70715903,
                                           70715902,
                                            //... (all photoIds in this group)
                                ],
                    "updated": "2015-08-11T10:40:23Z",
                    "userId": 4411
                  }
               }, ...
            {
                 "type": "album",
                 "album": { ... }
               }, ...
        
```
