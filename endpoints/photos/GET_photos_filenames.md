# GET /photos/filenames
***
`/photos/filenames`

### Description
***
Retrieves the authenticated user's original filenames.

### Parameters
***


### Response
***

```javascript
{
    "33179128": {
        "originalFilename": "8A0C594E-444D-4F48-8611-DC831822F92F",
        "photoFilteredHighRes": false,
        "photoUnfilteredHighRes": false
    },
    "33416110": {
        "originalFilename": "998DC1F7-7082-4236-B360-5EAB4F555EED",
        "photoFilteredHighRes": true,
        "photoUnfilteredHighRes": false
    }
}
```

200 and an array of photos with their associated store original filenames.
