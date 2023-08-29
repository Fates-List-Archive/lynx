
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

## Add Pack
### POST `https://fates-api.select-list.xyz`/users/{id}/packs

Creates a bot pack. 

- Set ``id`` to empty string, 
- Set ``created_at`` to any datetime
- In user and bot, only ``id`` must be filled, all others can be left empty string
but must exist in the object

**Path Parameters**

- **id** => i64 [0]




**Request Body**

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



**Request Body Example**

```json
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
```


**Response Body**

- **done** => bool [true]
- **reason** => None (unknown value type)
- **context** => None (unknown value type)



**Response Body Example**

```json
{
    "done": true,
    "reason": null,
    "context": null
}
```


**Authorization Needed** | [User](#authorization)


## Edit Pack
### PATCH `https://fates-api.select-list.xyz`/users/{id}/packs

Edits a bot pack. 

- Set ``id`` to the pack id that is to be editted, 
- Set ``created_at`` to any datetime
- In user and bot, only ``id`` must be filled, all others can be left empty string
but must exist in the object

**Path Parameters**

- **id** => i64 [0]




**Request Body**

- **id** => string ["f6660072-3722-4efa-b9f1-4e0b655e0c84"]
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



**Request Body Example**

```json
{
    "id": "f6660072-3722-4efa-b9f1-4e0b655e0c84",
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
```


**Response Body**

- **done** => bool [true]
- **reason** => None (unknown value type)
- **context** => None (unknown value type)



**Response Body Example**

```json
{
    "done": true,
    "reason": null,
    "context": null
}
```


**Authorization Needed** | [User](#authorization)


## Delete Pack
### DELETE `https://fates-api.select-list.xyz`/users/{user_id}/packs/{pack_id}

Deletes a bot pack. 

- Set ``pack_id`` to the pack id that is to be editted
- This endpoint may not always delete the pack in question in certain cases (pack not existant)

**Path Parameters**

- **user_id** => i64 [0]
- **pack_id** => string ["e3f94e1b-435d-447c-99f5-73ed0bca30ec"]





**Response Body**

- **done** => bool [true]
- **reason** => None (unknown value type)
- **context** => None (unknown value type)



**Response Body Example**

```json
{
    "done": true,
    "reason": null,
    "context": null
}
```


**Authorization Needed** | [User](#authorization)


