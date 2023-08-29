
**API URL**: ``https://fates-api.select-list.xyz``

**Widgets Documentation:** ``https://fates-lynx.select-list.xyz/widgets`` 

## Authorization

- **Bot:** These endpoints require a bot token. 
You can get this from Bot Settings. Make sure to keep this safe and in 
a .gitignore/.env. A prefix of `Bot` before the bot token such as 
`Bot abcdef` is supported and can be used to avoid ambiguity but is not 
required. The default auth scheme if no prefix is given depends on the
endpoint: Endpoints which have only one auth scheme will use that auth 
scheme while endpoints with multiple will always use `Bot` for 
backward compatibility

- **Server:** These endpoints require a server
token which you can get using ``/get API Token`` in your server. 
Same warnings and information from the other authentication types 
apply here. A prefix of ``Server`` before the server token is 
supported and can be used to avoid ambiguity but is not required.

- **User:** These endpoints require a user token. You can get this 
from your profile under the User Token section. If you are using this 
for voting, make sure to allow users to opt out! A prefix of `User` 
before the user token such as `User abcdef` is supported and can be 
used to avoid ambiguity but is not required outside of endpoints that 
have both a user and a bot authentication option such as Get Votes. 
In such endpoints, the default will always be a bot auth unless 
you prefix the token with `User`. **A access token (for custom clients)
can also be used on *most* endpoints as long as the token is prefixed with 
``Frostpaw``**

- **Special:** These endpoint employ their own authentication system (such as ``slwebset``)

## Base Response

A default API Response will be of the below format:

```json
{
    done: false | true,
    reason: "" | null,
    context: "" | null
}
```

## Get Server
### GET `https://fates-api.select-list.xyz`/servers/{id}

Fetches server information given a server/guild ID. If not found, 404 will be returned. 

- *``long_description/css`` is sanitized with ammonia by default, use `long_description_raw` if you want the unsanitized version*
- All responses are cached for a short period of time. There is *no* way to opt out unlike API v2
- Some fields have been renamed or removed
- ``invite_link`` is returned, however is always None unless ``Frostpaw-Invite`` header is set which then pushes you into 
server privacy restrictions. **Note that when fetching invite links, requires login to join is now enabled by default for all new servers**
                
**Set the Frostpaw header if you are a custom client. This is also needed for invites to work**

**Path Parameters**

- **id** => i64 [0]





**Response Body**

- **user** => Struct User 
	- **id** => string [""]
	- **username** => string [""]
	- **disc** => string [""]
	- **avatar** => string [""]
	- **bot** => bool [false]
	- **status** => string ["Unknown"]



- **owner** => Struct User 
	- **id** => string [""]
	- **username** => string [""]
	- **disc** => string [""]
	- **avatar** => string [""]
	- **bot** => bool [false]
	- **status** => string ["Unknown"]



- **description** => string [""]
- **tags** => (Array) 
- **long_description_type** => i32 [1]
- **long_description** => string [""]
- **long_description_raw** => string [""]
- **vanity** => (Optional) string ["server-vanity"]
- **guild_count** => i64 [0]
- **invite_amount** => i32 [0]
- **invite_link** => (Optional) string ["Only present if ``Frostpaw-Invite`` header is set"]
- **created_at** => string ["1970-01-01T00:00:00Z"]
- **state** => i32 [0]
- **flags** => (Array) 
- **css** => string [""]
- **css_raw** => string ["unsanitized css"]
- **extra_links** => Map (key/value)  
	- **key**
 => string ["value"]



- **banner_card** => (Optional) string ["https://frostpaw.com/assets/img/banner-card.png"]
- **banner_page** => (Optional) string ["https://frostpaw.com/assets/img/banner-page.png"]
- **votes** => i64 [0]
- **total_votes** => i64 [0]



**Response Body Example**

```json
{
    "user": {
        "id": "",
        "username": "",
        "disc": "",
        "avatar": "",
        "bot": false,
        "status": "Unknown"
    },
    "owner": {
        "id": "",
        "username": "",
        "disc": "",
        "avatar": "",
        "bot": false,
        "status": "Unknown"
    },
    "description": "",
    "tags": [],
    "long_description_type": 1,
    "long_description": "",
    "long_description_raw": "",
    "vanity": "server-vanity",
    "guild_count": 0,
    "invite_amount": 0,
    "invite_link": "Only present if ``Frostpaw-Invite`` header is set",
    "created_at": "1970-01-01T00:00:00Z",
    "state": 0,
    "flags": [],
    "css": "",
    "css_raw": "unsanitized css",
    "extra_links": {
        "key": "value"
    },
    "banner_card": "https://frostpaw.com/assets/img/banner-card.png",
    "banner_page": "https://frostpaw.com/assets/img/banner-page.png",
    "votes": 0,
    "total_votes": 0
}
```


**Authorization Needed** | None


## Random Server
### GET `https://fates-api.select-list.xyz`/random-server

Fetches a random server on the list

Example:
```py
import requests

def random_server():
    res = requests.get(api_url"/random-server")
    json = res.json()
    if res.status != 200:
        # Handle an error in the api
        ...
    return json
```



**Response Body**

- **guild_count** => i64 [30]
- **description** => string ["My description"]
- **banner** => string ["My banner or default banner url"]
- **votes** => i64 [40]
- **state** => i32 [3]
- **user** => Struct User 
	- **id** => string [""]
	- **username** => string [""]
	- **disc** => string [""]
	- **avatar** => string [""]
	- **bot** => bool [false]
	- **status** => string ["Unknown"]



- **flags** => (Array) 
- **created_at** => string ["2023-08-29T15:17:52.572840076Z"]



**Response Body Example**

```json
{
    "guild_count": 30,
    "description": "My description",
    "banner": "My banner or default banner url",
    "votes": 40,
    "state": 3,
    "user": {
        "id": "",
        "username": "",
        "disc": "",
        "avatar": "",
        "bot": false,
        "status": "Unknown"
    },
    "flags": [],
    "created_at": "2023-08-29T15:17:52.572840076Z"
}
```


**Authorization Needed** | None


