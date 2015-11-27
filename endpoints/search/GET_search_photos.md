# GET /search/photos   
***
`/search/photos`

### Description
***
Retrieves an array containing photos

### Parameters
***

|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**q**|a keyword to search for|string|||
|**languageCode**|two-letter identification of the search language|string||en|
|**searchVersion**|switch the search logic used for serving the search: see below for details |int||3|
|**searchFields**|which fields to search on: see below for details|Array[string]||all|
|**userId**|filter photos by a specific user|int|||
|**albumId**|filter photos tagged with a specific album|int|||
|**sizes**|filter photos that respect certain size limitations; possible options are `small`, `medium` and `large`|Array[string]|||
|**minWidth**, **minHeight**|filter photos over `width`x`height`; must be used together|int|||
|**uploadedBefore**|filter photos uploaded before the provided ISO date (`yyyy-MM-dd`)|string (ISO date format)|||
|**uploadedAfter**|filter photos uploaded after the provided ISO date|string(ISO date)|||
|**formats**|filter photos that respect certain format limitations; possible options are `portrait`, `landscape`, `square`, `widescreen` and `panorama`|Array[string]|||
|**latitude**|filter by proximity to a geopoint (requires longitude)|float||
|**longitude**|filter by proximity to a geopoint (requires latitude)|float||||
|**marketStatus**|filters by market status, options are `available`, `not_available`, `commercial` or `editorial`|string||||
|**includeHidden**|include photos flagged as hidden|boolean||false|
|**includeBlacklisted**|include photos flagged as blacklisted|boolean||false|
|**includeMeta**|in case `userId` or `albumId` filters are provided, it includes the corresponding entities under the `user` and `album` fields respectively|boolean||false|
|**detailed**| If true, allow inclusion of details|boolean||1|
|**includeComments**| If true, returns the latest two comments of a photo inline|boolean||1|
|**includeLikers**|If true, returns the latest two likers of a photo|boolean||1|
|**numComments**|the number of comments to include in the response|integer||2|
|**numLikers**|the number of likers to include in the response|integer||1|
|**includeAlbums**| If true, includes the albums this photo is part of|boolean||1|
|**userDetails**| If true, includes the detailed profile of the photo's owner|boolean||0|
|**includePeople**|If true, returns the people tagged in this photo photo|boolean||1|
|**numPeople**|the number of tagged people to include in the response|integer||10|
|**simpleDescription**|If true, returns a simple, human-readable photo description|boolean||0|
|**source**|Source of the search (used for tracking), 1 = Web-Market, 2 = Web-Community, 3 = Mobile|integer|No|1|
|**limit**|num of items to return|integer||10|
|**offset**|offset of items to start at|integer||0|
|**sort**|sort order results. possible values are _chrono_/_chronological_ (date), _aesthetics_ (aesthetic value), _relevance_|string||relevance|

* `searchVersion` allows to use older or newer logic for search
  *  `3` uses the `relevance v2` index and related logic with `recognition v4`
 
* `searchFields` specifies over which fields photos should be searched for; it can consist of a single parameter or an array specifying the list of possibilities:
  * `all` (default) include all fields in the search,
  * `user` allows to search over the user fields (created by, or tagged in),
  * `description` allows to search over the user-generated tags (or topics, or albums, or streams)
  * `getty` searches over the getty fields (getty tags and headline),
  * `deepLearning` and `impala` allow to search over the two recognition services' tags respectively,
  * `taxonomy` also includes taxonomy fields when querying `getty`, `deepLearning`, `impala` and `deepLearning`.

#### Deprecated parameters
|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**grayscale**|get only black and white photos|boolean|||
|**filter**|name of the (EyeEm) filter to filter by|string|||
|**frame**|name of the (EyeEm) frame to filter by|string|||
|**format**|filter photos by a specific format (portrait, landscape, square, panorama)|string|||
|**size**|filter photos by size (_xl_, _l_, _m_, _s_). _unknown_ is used for pictures with incorrect sizes|string||
|**color**|filter by a specific color [H-S-L]|string||
|**venueType**|get only photos taken at a specific type of venue (name)|string|||
|**venueTypeId**|get only photos taken at a specific type of venue (id)|string||
|**weather**|filter by weather type (clear, cloudy, fog, rain, snow)|string|||
|**camMake**|filter by manufacturer (ex: apple)|string|||
|**camModel**|filter by device (ex: iphone 5c)|string|||
|**camSoftware**|filter by exif cam software|string|||
|**people**|wether people should be present in the picture or not|boolean|||
|**peopleCard**|the amount of people the returned photos should contain, choosen from `gtone` (more then one), `few`, `many`|string|||
|**aggs**| If present, return aggregations together with the photo set|boolean|||

### Response
***

200 and an array containing photos
