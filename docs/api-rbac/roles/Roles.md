The resource routes belonging to this module are:

- /roles (**POST**)
- /roles (**GET**)
- /roles/{id} (**GET**)
- /roles/{id} (**PATCH**)
- /roles/{id} (**DELETE**)

**For more info you can go to `yourapiurl/docs#/Roles/`**

# Create Role

## Request

To create a role you simply need to send a post request to de `/role` endpoint with the following payload in `JSON`  format:

```json
{
    "data": [
        {
            "name": "admin4"
        }
    ]
}
```

You simply need to pass in an array of `objects`  containing the name of the role.This will then create all roles in the array. If you only need to insert one role simply pass in one `object` in the array

**NOTE : The api will not insert duplicate roles. It will simply ignore it.**

## Response

If the items are inserted the API will respond with an object containing a count where count represents the amount of records it has inserted

```json
{
    "count": 1
}

```


# GET Role

## Request

To get all roles you simply need to send a `GET` request to the `/role` endpoint.

## Response

The api will respond with an `array` of  `objects` containing information about the role.

```json
[
    {
        "id": 1,
        "name": "admin",
        "createdAt": "2023-01-22T17:02:30.982Z",
        "updatedAt": "2023-01-22T17:02:30.982Z"
    },
    {
        "id": 2,
        "name": "user",
        "createdAt": "2023-01-22T17:04:16.614Z",
        "updatedAt": "2023-01-22T17:04:16.614Z"
    },
]
```


# Update Role

## Request

To update a `role` you will have to make a `PATCH` request to `/roles/{id}` where `{id}` is the id of the role you wish to update. You will have to send an `object` in the body containing the new name of the role.

```json
{
    "name": "admin2"
}
```

## Response

After a successfull `PATCH` request you will receive the updated `role` as a response.

```json
{
    "id": 1,
    "name": "admin2",
    "createdAt": "2023-01-22T17:02:32.345Z",
    "updatedAt": "2023-01-23T19:49:46.683Z"
}
```


# Delete Role

## Request

To delete a role simply make a `DELETE` request to  `/roles/{id}` where `{id}` is the id of the role you wish to delete. 

```json

NO REQUEST BODY

```


## Response

After a successfull `DELETE` request you will receive the deleted `role` as a response.

```json
{
    "id": 2,
    "name": "test",
    "createdAt": "2023-01-22T17:04:16.614Z",
    "updatedAt": "2023-01-22T17:04:16.614Z"
}
```
