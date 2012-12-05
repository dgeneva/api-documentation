# Photo Resources

    PUT photos/update

## Description
Updates multiple photos.

***

## Requires authentication
**[OAuth][]**

***

## Parameters
- **photos** _(required)_ - A list of photos and their attributes to update

***

## Return format
Photo information in **[full format][]**.

***

## Errors
All known errors cause the resource to return HTTP error code header together with a JSON array containing at least 'status' and 'error' keys describing the source of error.

- **403 Forbidden** — You do not own the blog post you are trying to update.
- **404 Not Found** — The requested blog post does not exist or was deleted.
- **422 Unprocessable Entity** — One or more of the required fields didn't include valid data.

***

## Example
**Request**

    PUT v1/photos/10000275?photo[1][name]=Hello&photo[1][description]=My+photo+description&photo[2][name]=My+Photo

**Return**
``` json
{
  "body":"I went on a vacation to Hawaii",
  "created_at":"2011-10-17T18:07:31Z",
  "id":30,
  "latitude":null,
  "longitude":null,
  "tags":"",
  "title":"My Vacation",
  "user":{
    "city":null,
    "country":null,
    "firstname":"Ian",
    "id":76,
    "lastname":"Sobolev",
    "upgrade_status":0,
    "username":"iansobolev",
    "fullname":"Ian Sobolev",
    "userpic_url":"/graphics/userpic.png"
  },
  "photos": [
    {
      "category": 0,
      "created_at": "2011-10-17T18:37:18Z",
      "id": 251,
      "name": "At the beach",
      "rating": 0,
      "image_url": "http://pcdn.500px.net/251/c636d054379a5496338ef153920be5b23bee1e9a/4.jpg",
      "votes_count": 0
    }, {
      "category": 0,
      "created_at": "2011-10-17T18:37:18Z",
      "id": 251,
      "name": "My Vacation Photo",
      "rating": 0,
      "image_url": "http://pcdn.500px.net/251/c636d054379a5496338ef153920be5b23bee1e9a/4.jpg",
      "votes_count": 0
    }
  ]
}
```

[OAuth]: https://github.com/500px/api-documentation/tree/master/authentication
[full format]: https://github.com/500px/api-documentation/blob/master/basics/formats_and_terms.md#full-format
