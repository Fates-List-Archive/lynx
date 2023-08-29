
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

## Index
### GET `https://fates-api.select-list.xyz`/index
Returns the index for bots and servers
**Query Parameters**

- **target_type** => i32 [1]






**Response Body**

- **random** => Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571342489Z"]



- **new** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571322234Z"]



- **top_voted** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571322234Z"]



- **certified** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571322234Z"]



- **tags** => (Array) Struct Tag 
	- **name** => string [""]
	- **iconify_data** => string [""]
	- **id** => string [""]
	- **owner_guild** => None (unknown value type)



- **features** => (Array) Struct Feature 
	- **id** => string [""]
	- **name** => string [""]
	- **viewed_as** => string [""]
	- **description** => string [""]






**Response Body Example**

```json
{
    "random": {
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
        "created_at": "2023-08-29T15:17:52.571342489Z"
    },
    "new": [
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
            "created_at": "2023-08-29T15:17:52.571322234Z"
        }
    ],
    "top_voted": [
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
            "created_at": "2023-08-29T15:17:52.571322234Z"
        }
    ],
    "certified": [
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
            "created_at": "2023-08-29T15:17:52.571322234Z"
        }
    ],
    "tags": [
        {
            "name": "",
            "iconify_data": "",
            "id": "",
            "owner_guild": null
        }
    ],
    "features": [
        {
            "id": "",
            "name": "",
            "viewed_as": "",
            "description": ""
        }
    ]
}
```


**Authorization Needed** | None


## Ping
### GET `https://fates-api.select-list.xyz`/ping
Returns nothing




**Authorization Needed** | None


## Set Server Listing By Web
### POST `https://fates-api.select-list.xyz`/slwebset
Sets the server listing on the web (after ``/webset`` command). Set ``Authorization`` to the token given by webset


**Request Body**

- **value** => string [""]



**Request Body Example**

```json
{
    "value": ""
}
```


**Response Body**

- **done** => bool [true]
- **reason** => None (unknown value type)
- **context** => (Optional) string ["https://discord.com/........."]



**Response Body Example**

```json
{
    "done": true,
    "reason": null,
    "context": "https://discord.com/........."
}
```


**Authorization Needed** | [Special](#authorization)


## Get Experiment List
### GET `https://fates-api.select-list.xyz`/experiments
Returns all currently available experiments



**Response Body**

- **user_experiments** => (Array) Struct UserExperimentListItem 
	- **name** => string ["Unknown"]
	- **value** => i32 [0]






**Response Body Example**

```json
{
    "user_experiments": [
        {
            "name": "Unknown",
            "value": 0
        }
    ]
}
```


**Authorization Needed** | None


## Resolve Vanity
### GET `https://fates-api.select-list.xyz`/code/{code}
Resolves the vanity for a bot/server in the list

**Path Parameters**

- **code** => string ["my-vanity"]





**Response Body**

- **target_type** => string ["bot | server"]
- **target_id** => string ["0000000000"]



**Response Body Example**

```json
{
    "target_type": "bot | server",
    "target_id": "0000000000"
}
```


**Authorization Needed** | None


## Get Partners
### GET `https://fates-api.select-list.xyz`/partners
Get current partnership list



**Response Body**

- **partners** => (Array) Struct Partner 
	- **id** => string ["0"]
	- **name** => string ["My development"]
	- **owner** => string ["12345678901234567"]
	- **image** => string [""]
	- **description** => string ["Some random description"]
	- **links** => Struct PartnerLinks 
		- **discord** => string ["https://discord.com/lmao"]
		- **website** => string ["https://example.com"]






- **icons** => Struct PartnerLinks 
	- **discord** => string [""]
	- **website** => string [""]






**Response Body Example**

```json
{
    "partners": [
        {
            "id": "0",
            "name": "My development",
            "owner": "12345678901234567",
            "image": "",
            "description": "Some random description",
            "links": {
                "discord": "https://discord.com/lmao",
                "website": "https://example.com"
            }
        }
    ],
    "icons": {
        "discord": "",
        "website": ""
    }
}
```


**Authorization Needed** | None


## Search List
### GET `https://fates-api.select-list.xyz`/search?q={query}

Searches the list based on a query named ``q``. 
        
Using -1 for ``gc_to`` will disable ``gc_to`` field
**Query Parameters**

- **q** => string ["mew"]
- **gc_from** => i64 [1]
- **gc_to** => i64 [-1]






**Response Body**

- **bots** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571581301Z"]



- **servers** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571581901Z"]



- **profiles** => (Array) Struct SearchProfile 
	- **banner** => string [""]
	- **description** => string [""]
	- **user** => Struct User 
		- **id** => string [""]
		- **username** => string [""]
		- **disc** => string [""]
		- **avatar** => string [""]
		- **bot** => bool [false]
		- **status** => string ["Unknown"]






- **packs** => (Array) Struct BotPack 
	- **id** => string ["0"]
	- **name** => string [""]
	- **description** => string [""]
	- **icon** => string [""]
	- **banner** => string [""]
	- **resolved_bots** => (Array) Struct ResolvedPackBot 
		- **user** => Struct User 
			- **id** => string [""]
			- **username** => string [""]
			- **disc** => string [""]
			- **avatar** => string [""]
			- **bot** => bool [false]
			- **status** => string ["Unknown"]



		- **description** => string [""]



	- **owner** => Struct User 
		- **id** => string [""]
		- **username** => string [""]
		- **disc** => string [""]
		- **avatar** => string [""]
		- **bot** => bool [false]
		- **status** => string ["Unknown"]



	- **created_at** => string ["1970-01-01T00:00:00Z"]



- **tags** => Struct SearchTags 
	- **bots** => (Array) Struct Tag 
		- **name** => string [""]
		- **iconify_data** => string [""]
		- **id** => string [""]
		- **owner_guild** => None (unknown value type)



	- **servers** => (Array) Struct Tag 
		- **name** => string [""]
		- **iconify_data** => string [""]
		- **id** => string [""]
		- **owner_guild** => None (unknown value type)









**Response Body Example**

```json
{
    "bots": [
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
            "created_at": "2023-08-29T15:17:52.571581301Z"
        }
    ],
    "servers": [
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
            "created_at": "2023-08-29T15:17:52.571581901Z"
        }
    ],
    "profiles": [
        {
            "banner": "",
            "description": "",
            "user": {
                "id": "",
                "username": "",
                "disc": "",
                "avatar": "",
                "bot": false,
                "status": "Unknown"
            }
        }
    ],
    "packs": [
        {
            "id": "0",
            "name": "",
            "description": "",
            "icon": "",
            "banner": "",
            "resolved_bots": [
                {
                    "user": {
                        "id": "",
                        "username": "",
                        "disc": "",
                        "avatar": "",
                        "bot": false,
                        "status": "Unknown"
                    },
                    "description": ""
                }
            ],
            "owner": {
                "id": "",
                "username": "",
                "disc": "",
                "avatar": "",
                "bot": false,
                "status": "Unknown"
            },
            "created_at": "1970-01-01T00:00:00Z"
        }
    ],
    "tags": {
        "bots": [
            {
                "name": "",
                "iconify_data": "",
                "id": "",
                "owner_guild": null
            }
        ],
        "servers": [
            {
                "name": "",
                "iconify_data": "",
                "id": "",
                "owner_guild": null
            }
        ]
    }
}
```


**Authorization Needed** | None


## Search Tags
### GET `https://fates-api.select-list.xyz`/search-tags?q={query}
Searches the list based on a tag named ``q``.
**Query Parameters**

- **q** => string ["mew"]






**Response Body**

- **bots** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571706149Z"]



- **servers** => (Array) Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571706785Z"]



- **profiles** => (Array) Struct SearchProfile 
	- **banner** => string [""]
	- **description** => string [""]
	- **user** => Struct User 
		- **id** => string [""]
		- **username** => string [""]
		- **disc** => string [""]
		- **avatar** => string [""]
		- **bot** => bool [false]
		- **status** => string ["Unknown"]






- **packs** => (Array) Struct BotPack 
	- **id** => string ["0"]
	- **name** => string [""]
	- **description** => string [""]
	- **icon** => string [""]
	- **banner** => string [""]
	- **resolved_bots** => (Array) Struct ResolvedPackBot 
		- **user** => Struct User 
			- **id** => string [""]
			- **username** => string [""]
			- **disc** => string [""]
			- **avatar** => string [""]
			- **bot** => bool [false]
			- **status** => string ["Unknown"]



		- **description** => string [""]



	- **owner** => Struct User 
		- **id** => string [""]
		- **username** => string [""]
		- **disc** => string [""]
		- **avatar** => string [""]
		- **bot** => bool [false]
		- **status** => string ["Unknown"]



	- **created_at** => string ["1970-01-01T00:00:00Z"]



- **tags** => Struct SearchTags 
	- **bots** => (Array) Struct Tag 
		- **name** => string [""]
		- **iconify_data** => string [""]
		- **id** => string [""]
		- **owner_guild** => None (unknown value type)



	- **servers** => (Array) Struct Tag 
		- **name** => string [""]
		- **iconify_data** => string [""]
		- **id** => string [""]
		- **owner_guild** => None (unknown value type)









**Response Body Example**

```json
{
    "bots": [
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
            "created_at": "2023-08-29T15:17:52.571706149Z"
        }
    ],
    "servers": [
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
            "created_at": "2023-08-29T15:17:52.571706785Z"
        }
    ],
    "profiles": [
        {
            "banner": "",
            "description": "",
            "user": {
                "id": "",
                "username": "",
                "disc": "",
                "avatar": "",
                "bot": false,
                "status": "Unknown"
            }
        }
    ],
    "packs": [
        {
            "id": "0",
            "name": "",
            "description": "",
            "icon": "",
            "banner": "",
            "resolved_bots": [
                {
                    "user": {
                        "id": "",
                        "username": "",
                        "disc": "",
                        "avatar": "",
                        "bot": false,
                        "status": "Unknown"
                    },
                    "description": ""
                }
            ],
            "owner": {
                "id": "",
                "username": "",
                "disc": "",
                "avatar": "",
                "bot": false,
                "status": "Unknown"
            },
            "created_at": "1970-01-01T00:00:00Z"
        }
    ],
    "tags": {
        "bots": [
            {
                "name": "",
                "iconify_data": "",
                "id": "",
                "owner_guild": null
            }
        ],
        "servers": [
            {
                "name": "",
                "iconify_data": "",
                "id": "",
                "owner_guild": null
            }
        ]
    }
}
```


**Authorization Needed** | None


## Mini Index
### GET `https://fates-api.select-list.xyz`/mini-index

Returns a mini-index which is basically a Index but with only ``tags``
and ``features`` having any data. Other fields are empty arrays/vectors.

This is used internally by sunbeam for the add bot system where a full bot
index is too costly and making a new struct is unnecessary.
                



**Response Body**

- **random** => Struct IndexBot 
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
	- **created_at** => string ["2023-08-29T15:17:52.571823485Z"]



- **new** => (Array) 
- **top_voted** => (Array) 
- **certified** => (Array) 
- **tags** => (Array) Struct Tag 
	- **name** => string [""]
	- **iconify_data** => string [""]
	- **id** => string [""]
	- **owner_guild** => None (unknown value type)



- **features** => (Array) Struct Feature 
	- **id** => string [""]
	- **name** => string [""]
	- **viewed_as** => string [""]
	- **description** => string [""]






**Response Body Example**

```json
{
    "random": {
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
        "created_at": "2023-08-29T15:17:52.571823485Z"
    },
    "new": [],
    "top_voted": [],
    "certified": [],
    "tags": [
        {
            "name": "",
            "iconify_data": "",
            "id": "",
            "owner_guild": null
        }
    ],
    "features": [
        {
            "id": "",
            "name": "",
            "viewed_as": "",
            "description": ""
        }
    ]
}
```


**Authorization Needed** | None


