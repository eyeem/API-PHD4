#2.3.3 - March 2015

- Featured Albums in Discover
- Enabled Photo Sold & Getty Approval news
- Cut Number of Items sent in Aggregated News

#2.3.2 - 07.09.2014 Safety Milestone
- hidden and blacklisted are now part of the simple response (users, albums)
- hidden and blacklisted added to photo object (and response)
- added POST /photos/{id}/hide?hide={bool} [admin only]
- added POST /photos/{id}/blacklist?blacklist={bool} [admin and authed users]
- user option to set/unset NSFW flag for user (show_nsfw_content)

#2.3.2
- new model for (lightweight) missions
- thumbUrl removed from albums, replaced by coverPhoto
- coverphoto added to users
- added option to change cover_photo_id for albums

#2.3.1
- introduce id obfuscation for users, photos, albums
- added /users/{me}/unlock endpoint to support share to unlock feature.
#2.3.0
- remove emailNotifications / pushNotifications flags from user
- add ab_friends_in_disocver, ab_show_friends, ab_album_list flags in users/newsSettings

#2.2.1
- cdn.eyeem.com instead of www.eyeem.com for thumbs
- ab_friends_in_discover flag in discover feed.

#2.2.0
- new topic suggestions format for venues
- new discover types
- new param filter=favorited,trending,nearby,contributed etc... in discover
- discover now returns current city, nearest venue and weather information
- hoursOfDay param now part of default API Headers
- Discover is localized to Accept-Language header, defaults to 'en'
- Album and User Photos have sort=top (ordered by popularity) and new pagination (before/after)
- added /albums/onboarding endpoint (GET,POST) for subscribing to topical sets


#2.1.0

 - tagged people in news
 - new photo description parameters
 - facebook sharing settings are 0 by default
 - new upload
