# GET /users/recommended/photos

### Description

Get latest photos from recommended users.

### Parameters

#### Query Parameters

| **parameter**  | **description** | **type** | **required?** | **default** | **notes**
|----------------|-----------------|----------|---------------|-------------|----------
| **offset**     |                 |   int    |               |      0      | pagination
| **limit**      |                 |   int    |               |     30      | pagination

#### Format Parameters

All default photos format parameters.

| **parameter**            | **description** | **type** | **required?** | **default** | **notes**
|--------------------------|-----------------|----------|---------------|-------------|----------
| **detailed**             |                 |   bool   |               |      1      |
| **includeComments**      |                 |   bool   |               |    false    |
| **numComments**          |                 |   int    |               |      2      |
| **includeLikers**        |                 |   bool   |               |    false    |
| **numLikers**            |                 |   int    |               |      1      |
| **includePeople**        |                 |   bool   |               |    false    |
| **numPeople**            |                 |   int    |               |      4      |
| **includeAlbums**        |                 |   bool   |               |    false    |
| **userDetails**          |                 |   bool   |               |    false    |
| **simpleDescription**    |                 |   bool   |               |    false    |
| **photoHighRes**         |                 |   bool   |               |    false    |
| **marketStatus**         |                 |   bool   |               |    false    |
| **nsfw**                 |                 |   bool   |               |    false    |

### Response

200 and and a dictionary containing limit, offset, total and an array of photo objects

```
{
    "photos": {
        "offset": 0,
        "limit": 30,
        "total": 1,
        "items": [
            {
                "id": "48418933",
                "file_id": "3f2d1b169f7180c78cc0bc3d295608e3747f3843-1412520428",
                "thumbUrl": "http://cdn.eyeem.com/thumb/h/100/3f2d1b169f7180c78cc0bc3d295608e3747f3843-1412520428?highRes=true",
                "photoUrl": "http://cdn.eyeem.com/thumb/640/480/3f2d1b169f7180c78cc0bc3d295608e3747f3843-1412520428?highRes=true",
                "webUrl": "http://www.eyeem.com/p/48418933",
                "width": 2448,
                "height": 3264,
                "updated": "2014-10-05T16:47:26+0200",
                "hidden": false,
                "blacklisted": false
            }
        ]
    }
}
```
