#API data model and object types
***

Below are the possible representation of [users](#users), [albums](#albums), [photos](#photos), [comments](#comments), [topics](#topics), [news](#news), and [services](#services).
The objects and variables are hopefully self-explanatory, but we will describe those that might be not so clear.

For users, albums and photos, we will also provide the simplest valid object that the server might send back, as well as the possible dictionary names that would contain items of the respective objects.

##Users
***

```json
{
  "user": {
    "id": "1013",
    "nickname": "ramz",
    "fullname": "Ramzi Rizk",
    "webUrl": "http://www.eyeem.com/u/ramz",
    "thumbUrl": "http://www.eyeem.com/thumb/ad12f89204332f639524a3c4c7b14d8d02bbab67-1357734675/sq/50",
    "photoUrl": "http://www.eyeem.com/thumb/ad12f89204332f639524a3c4c7b14d8d02bbab67-1357734675/sq/200",
    "totalPhotos": 1993,
    "totalFollowers": 1714,
    "totalFriends": 1907,
    "totalLikedAlbums": 139,
    "totalLikedPhotos": 9502,
    "description": "EyeEm Ramz. EyeEm Happy! Srsly. Choo choo!!",
    "email": "ramz@eyeem.com",
    "file_id": "ad12f89204332f639524a3c4c7b14d8d02bbab67-1357734675",
    "services": {
      "facebook": {
        "third_party_id": "j7ABpetM5kn1D2TwsHv-OW1tuTM",
        "id": "642412756",
        "access_token": "CAAB9pKooVA4BAJHJ9OZCej289LwrbIDw06x1rjn1eZAPiaZBJWEL4vdwAMG9ZAgmszDrkA5RvNG4YBeDjC3H8wFZCLShnBwpSEPpUQxQyZC9hl9BLmJZBAtROZBpZCec7Vrt7PduoAj5kPH5X3gfxXowaGB4ZAAeJ434AZD",
        "publish_actions": true,
        "upload": false,
        "photolike": true,
        "photodiscover": false,
        "photocomment": true,
        "albumlike": false,
        "albumfavorite": true,
        "albumcontribution": false,
        "userfollow": true,
        "timelinepopup": true,
        "managedPages": [
          {
            "id": "150458201636928",
            "name": "I Am Rambo",
            "posting": 0
          },
          {
            "id": "369311466483832",
            "name": "EyeEm",
            "posting": 0
          },
          {
            "id": "168014246580820",
            "name": "Photo Hack Day",
            "posting": 0
          },
          {
            "id": "329045503624",
            "name": "sudanvotes",
            "posting": 0
          },
          {
            "id": "182029908477190",
            "name": "PoppupUp",
            "posting": 0
          },
          {
            "id": "22972653688",
            "name": "Cancer Research UK Race for Life",
            "posting": 0
          },
          {
            "id": "136689719690381",
            "name": "Pancäke",
            "posting": 0
          },
          {
            "id": "115244968563450",
            "name": "Berlin Startup Basketball League",
            "posting": 0
          },
          {
            "id": "165272473499096",
            "name": "Qualitocracy",
            "posting": 0
          },
          {
            "id": "170111226353716",
            "name": "Popped Up",
            "posting": 0
          },
          {
            "id": "175348109151117",
            "name": "PoppedUp",
            "posting": 0
          }
        ],
        "status": "active"
      },
      "twitter": {
        "id": "1742581",
        "nickname": "ramz",
        "status": "active"
      },
      "tumblr": {
        "status": "active"
      },
      "foursquare": {
       "status": "active"
      },
      "flickr": {
        "id": "18615422@N00",
        "nickname": "LeRamz",
        "status": "active"
      }
    },
    "newsSettings": {
      "push_photo_like": true,
      "push_photo_comment": true,
      "push_user_follower": true,
      "push_user_joined": true,
      "push_album_contributor": true,
      "push_photo_comment_mention": true,
      "email_photo_like": true,
      "email_photo_comment": true,
      "email_user_follower": true,
      "email_user_joined": true,
      "email_album_contributor": true,
      "email_photo_comment_mention": true,
      "email_weekly_newsletter": true,
      "push_album_invite": true,
      "email_album_invite": true,
      "facebook_upload": false,
      "facebook_photolike": true,
      "facebook_photodiscover": false,
      "facebook_photocomment": true,
      "facebook_albumlike": false,
      "facebook_albumfavorite": true,
      "facebook_userfollow": true,
      "facebook_timeline_popup": true,
      "facebook_albumcontribution": false,
      "email_newsletter": true,
      "web_onboarded": true,
      "web_banner_shown": true,
      "push_photo_tagged_person": true,
      "email_photo_tagged_person": true,
      "web_onboarding_step": 0,
      "onboarding_collections": true,
      "ab_friends_in_discover": false,
      "ab_show_friends": false,
      "ab_album_list": false,
      "show_nsfw_content": false   
    },
    "hidden": false,
    "blacklisted": false,
  }
}
```
#### Remarks
* Arrays of user items can have the following dictionary names as wrappers: `friends`, `contributors`, `followers`, `likers`, `users`
* The fields `email`, `emailNotifications`, `pushNotifications` and the `services` dictionary are only available for the authenticated user object

##Albums
***

```json
{
  "album": {
    "id": "17",
    "name": "Berlin",
    "type": "city",
    "thumbUrl": "http://www.eyeem.com/thumb/sq/200/4fbf551231917efbc913d5a689c982f8db2c5f7a-1358438528",
    "webUrl": "http://www.eyeem.com/a/17",
    "updated": "2013-07-12T20:03:29+0200",
    "location": {
      "latitude": "52.52437",
      "longitude": "13.41053",
      "countryCode": "DE",
      "countryAlbum": {
        "id": "23",
        "name": "Germany",
        "type": "country",
        "thumbUrl": "http://www.eyeem.com/thumb/sq/200/4fbf551231917efbc913d5a689c982f8db2c5f7a-1358438528",
        "webUrl": "http://www.eyeem.com/a/23",
        "updated": "2013-07-12T20:03:29+0200"
      },
      "facebookPage": {
        "id": "344409052313578",
        "name": "EyeEm Berlin"
      }
    },
    "totalPhotos": 116238,
    "totalLikers": 3367,
    "totalContributors": 6977,
    "hidden": false,
    "blacklisted": false
  }
}
```

#### Remarks
* Arrays of album items can have the following dictionary names as wrappers: `albums`, `likedAlbums`, `feedAlbums`
* Albums can have the following type: `tag`,`venue`,`city`,`country`
* extended album objects can also contain inline arrays of likers, contributors and photos

##Photos
***

```json
{
  "photo": {
    "id": "215058",
    "thumbUrl": "http://www.eyeem.com/thumb/h/100/70b5d5feefc5946bb7b912b8661c3329912fda3d-1328177792",
    "photoUrl": "http://www.eyeem.com/thumb/640/480/70b5d5feefc5946bb7b912b8661c3329912fda3d-1328177792",
    "webUrl": "http://www.eyeem.com/p/215058",
    "width": 1530,
    "height": 2048,
    "updated": "2012-02-02T10:16:33+0100",
    "user": {
      "id": "1013",
      "nickname": "ramz",
      "fullname": "Ramzi Rizk",
      "webUrl": "http://www.eyeem.com/u/ramz",
      "thumbUrl": "http://www.eyeem.com/thumb/sq/50/ad12f89204332f639524a3c4c7b14d8d02bbab67-1357734675",
      "photoUrl": "http://www.eyeem.com/thumb/sq/200/ad12f89204332f639524a3c4c7b14d8d02bbab67-1357734675",
      "description": "EyeEm Ramz. EyeEm Happy! Srsly. Choo choo!!"
    },
    "latitude": "52.53499985",
    "longitude": "13.40600014",
    "totalLikes": 13,
    "totalPeople": 0,
    "totalComments": 1,
    "description": "11:11 at Coffee to go [a:55744]",
    "hidden": false,
    "blacklisted": false
    "filter": "Magix",
    "frame": "Bround"
  }
}
```
#### Remarks
* Arrays of photo items can have the following dictionary names as wrappers: `photos`, `friendsPhotos`, `likedPhotos`
* extended photo objects can also contain inline arrays of likers, comments, albums and tagged people

##Comments
***

```json
{
  "comment": {
    "id": "7464179",
    "photoId": "15962932",
    "message": "@steph facundo esteban:)",
    "extendedMessage": "[user:24961] facundo esteban:)",
    "user": {
      "id": "341655",
      "nickname": "olgasteidl",
      "fullname": "Olga Steidl",
      "webUrl": "http://www.eyeem.com/u/olgasteidl",
      "thumbUrl": "http://www.eyeem.com/thumb/sq/50/4c5a57e62a74932ff1023b20edbb15d9281d6506-1368126732",
      "photoUrl": "http://www.eyeem.com/thumb/sq/200/4c5a57e62a74932ff1023b20edbb15d9281d6506-1368126732",
      "description": "I live. I shoot. I post. #startupgirl"
    },
    "mentionedUsers": [
      {
        "id": "24961",
        "nickname": "steph",
        "fullname": "Stephanie",
        "webUrl": "http://www.eyeem.com/u/steph",
        "thumbUrl": "http://www.eyeem.com/thumb/sq/50/4f3e2914d000952f956e52967f5763d35bd48e6f-1362159353",
        "photoUrl": "http://www.eyeem.com/thumb/sq/200/4f3e2914d000952f956e52967f5763d35bd48e6f-1362159353",
        "description": "Oh hai dere! I'm Stephanie and I work as Community Manager at EyeEm. Say hi here: stephanie@eyeem.com"
      }
    ],
    "updated": "2013-07-11T12:37:57+0200"
  }
}
```
### Remarks
* Comment objects always include a basic user object identifying the comment's author
* extended message includes the userIds of mentioned users, simple message returns the human-readable version.

##News
***
Single news items are still available from the API, but the recommended approach is to require aggregated news. Here's a sample news response:
The response header contains 

```json
{
  "news": {
    "limit": 30,
    "unseen": 8,
    "oldestId": "225774223",
    "newestId": "228852686",
    "total": 610
    "items" : { ARRAY of NEWS ITEMS }
  }
}

Every news item contains the following:

```json
      {
        "id": "19588",
        "itemType": "photo",
        "newsType": "like",
        "photo":{ PHOTO Object if available}
        "user":{ USER Object if available}
        "album":{ ALBUM Object if available}
        "comment":{ COMMENT Object if available}        
        "updated": "2012-02-03T15:11:20+0000"
      }
```

alternatively, if it's a blog post:

```json
      {
        "id": "19588",
        "itemType": "url",
        "newsType": "blogPost",
        "title": "New Blog Post:",
        "body": "Your Week on EyeEm",
        "thumbUrl": "http://blog.eyeem.com/coolimage.jpg",
        "url": "http://blog.eyeem.com/blogpostID",        
        "updated": "2012-02-03T15:11:20+0000",
      }
```

In case the news item is an aggregation, it additionally contains an `aggregation` object, that item specifies whether the aggregation was on a photo or on a user, and contains an array of photos/users respectively. In that case, the news item also contains an array of the aggregated news Ids:

```json
{
  "item": {the regular item},
  "aggregation": {
    "aggregated": true,
    "total": 2,
    "type": "photo",
    "photos": [ ARRAY OF PHOTOS ],
    "users": [ ARRAY OF USERS ]
  },
  "ids": [
    "225870335",
    "225870328"
  ]
}
```
### Remarks:
* itemType dictates what type of object the news item links to. Possible values: `photo`, `user`, `album`
* newsType dictates what type of notification this is. Possible values: `like`, `comment`, `follow`, `commentAfter`, `albumContributor`, `albumInvite`, `taggedPerson`, `fbFriend`, `twFriend`

##Services
***

```json
{
  "services": {
    "facebook": {
      "status": "active"
      "id": "12342335"
      "upload": true
      "primary": true
      "photolike": true
      "photocomment": true
      "albumlike": true
      "userfollow": true
    },
    "twitter": {
      "status": "active"
      "nickname": "EyeEm"
      "id": "12342335"
    },
    "foursquare": {
      "status": "active"
    },
    "tumblr": {
      "status": "active"
    },
    "flickr": {
      "status": "inactive"
    }
  }
}
```

##Contacts
***

```json
{
    "serviceType": "twitter",
    "serviceId": 105133786,
    "nickname": "thisislorenz",
    "fullname": "Lorenz Aschoff",
    "thumbUrl": "http://a1.twimg.com/profile_images/632871017/me_normal.png"
}
```

Or with a matching user:

```json
{
    "serviceType": "twitter",
    "serviceId": 105133786,
    "nickname": "thisislorenz",
    "fullname": "Lorenz Aschoff",
    "thumbUrl": "http://a1.twimg.com/profile_images/632871017/me_normal.png",
    "user": {
      "id": "8203",
      "fullname": "Mac Gyver",
      "nickname": null,
      "thumbUrl": "",
      "isFriend": false
    }
}
```



##Location (sub-object attached to location-based albums at the moment)
***

The location object always contains at least latitude and longitude, and depending on the album type, further embedded objects: 
* venue: has a simple city album, simple country album and a venueService object
* city: has a simple country album
* country: only has latitude and longitude

```json
location:{
    "latitude": 52.5031436,
    "longitude": 13.40083313,
    "cityAlbum":{
       ... simple album object
     },
    "countryAlbum":{
       ... simple album object
     },
    "venueService":{
       ... venue service object (see below)
     }
}
```


##Person
***
A person object is used to tag people from various services (fb, tw, eyeem) on a photo.

```json
{
  "serviceType": "eyeem",
  "serviceId": "1014",
  "fullname": "Flo Meissner",
  "nickname": "Flo",
  "thumbUrl": "http://www.eyeem.com/thumb/sq/50/a60ebe1fdddc4481aed8ac4381bca9ab5990b469-1357068992",
  "facebook": true,
  "twitter": true
}

```

##City / Country
***
A city/country object

```json
{
  "id": "2950159",
  "type": "city",
  "name": "Berlin",
  "ansiname": "Berlin",
  "district_code": "16",
  "country_id": "DE",
  "country_name": "Germany",
  "album_id": "17"
},
{
  "id": "DE",
  "type": "country",
  "country_name": "Germany",
  "album_id": "18"
}

```
