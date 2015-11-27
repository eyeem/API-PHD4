# GET /news 
***
`/news`

### Description
***
Retrieves the authenticated user's news items (aggregated), either the latest items, or any items newer than `newestId` or any items older than `oldestId`.


### Parameters
***

|parameter| description| type |required? |default|
|:---------|:--------------|:----------:|:------------:|:------------:|
|**limit**|num of news items to return|integer||30|
|**oldestId**|get X items older than this id|integer||0|
|**newestId**|get X items newer than this id|integer||0|

### Currently available news types
***

|backend news type| int identifier | item type | **string identifier (newsType)** | comment | auto push/And | auto push/iOS |
|:---------|:--------------|:----------:|:------------:|:------------:|:------------:|:------------:|:------------:|
PHOTO_LIKE | 1 | photo | like | | y | y |
USER_FOLLOW | 2 | user | follow | | y | y |
PHOTO_COMMENT | 3 | photo | comment | | y | y |
PHOTO_COMMENT_MENTION | 4 | photo | commentMention | | y | y |
ALBUM_CONTRIBUTOR | 5 | photo | albumContributor | | y | y |
ALBUM_INVITE | 6 | album | albumInvite | | y | y |
FRIEND_FACEBOOK | 7 | user | fbFriend | | y | y |
FRIEND_TWITTER | 8 | user | twFriend | | y | y |
BLOG_POST_URL | 9 | url | blogPost | | | |
PHOTO_COMMENT_AFTER | 10 | photo | commentAfter | | | |
PHOTO_TAGGED_PERSON | 11 | photo | taggedPerson | | y | y |
OTHER_URL | 12 | url | other | | | |
PAGE_DISCOVER | 13 | discover | page | | | |
PAGE_CAMERA | 14 | camera | page | | | |
PAGE_MISSIONS | 15 | missions | page | | y | y |
PAGE_PROFILE | 16 | profile | page | | | |
PAGE_ALBUM | 17 | album | page | | | |
PAGE_PHOTO | 18 | photo | page | | | |
PAGE_FRIENDS | 19 | friends | page | | | |
PAGE_POPULAR | 20 | popular | page | | | |
WEEKLY_POPULAR | 21 | photo | page | | | |
INSTA_IMPORTER | 22 | instagramImporter | page | | | |
INSTA_IMPORTED | 24 | instagramImported | page | | | |
PAGE_MISSION | 25 | mission | page | | y | y |
LICENSE_REQUEST | 26 | photo | licenseRequest | disabled | y | y |
MARKET_GETTY_APPROVAL | 27 | url | gettyApproval | disabled | | |
PHOTO_SOLD | 28 | photo | photoSold | **available from API v2.3.6** in aggregated form | y | y |
MARKET_URL | 29 | url | market | | | |
PHOTO_SOLD_GETTY | 30 | photo | photoSoldGetty | **available from API v2.3.6** in aggregated form | y | y |
PHOTO_SOLD_PARTNER | 31 | photo | photoSoldPartner | still in planning stage | | |

### Response
***

```json
{
    "version": "3",
    "news": {
        "limit": 30,
        "unseen": 0,
        "oldestId": "757226699",
        "newestId": "790425347",
        "total": 148,
        "items": [
            {
                "id": "790425347",
                "itemType": "photo",
                "newsType": "photoSoldGetty",
                "updated": "2015-08-06T10:43:40+0200",
                "seen": false,
                "photo": {
                    "id": "68815451",
                    "file_id": "d5632c85d43505c1c3172c22c3df584731e2c292-1436565240",
                    "thumbUrl": "http://cdn.eyeem.com/thumb/h/100/d5632c85d43505c1c3172c22c3df584731e2c292-1436565240",
                    "photoUrl": "http://cdn.eyeem.com/thumb/640/480/d5632c85d43505c1c3172c22c3df584731e2c292-1436565240",
                    "webUrl": "http://www.eyeem.com/p/68815451",
                    "width": 3264,
                    "height": 2448,
                    "updated": "2015-07-10T23:58:58+0200",
                    "hidden": false,
                    "blacklisted": false,
                    "openEdit": [],
                    "submittedToMarket": true
                }
            },
            {
                "id": "1225",
                "itemType": "url",
                "newsType": "blogPost",
                "updated": "2015-08-06T10:32:12+0200",
                "seen": true,
                "title": "EyeEm X Getty:",
                "thumbUrl": null,
                "body": "Congratulations, you sold a photo! Request payout now",
                "url": "https://www.eyeem.com/market/sell/payout?a=xxx"
            },
            {
                "id": "790425318",
                "itemType": "user",
                "newsType": "follow",
                "updated": "2015-07-31T16:56:22+0200",
                "seen": false,
                "user": {
                    "id": "13518003",
                    "nickname": "jonnytestgolem",
                    "fullname": "John Wellington Golem",
                    "webUrl": "http://www.eyeem.com/u/jonnytestgolem",
                    "thumbUrl": "http://cdn.eyeem.com/thumb/sq/50/f38331412d0bef4ba3d755da6665d1aaf7287ded-1408705392",
                    "photoUrl": "http://cdn.eyeem.com/thumb/sq/200/f38331412d0bef4ba3d755da6665d1aaf7287ded-1408705392",
                    "hidden": false,
                    "blacklisted": false,
                    "description": "Wow w wow w wow w w wow w wow w wow w w.",
                    "follower": true,
                    "following": false,
                    "restricted": false,
                    "blocked": false
                }
            }
        ]
    }
}
```

200 and a dictionary containing pagination info and an array of news items.
