The resource routes belonging to this module are:

- /roles/:id/permission (**POST**)
- /roles/:id/permission (**PATCH**)

# Assigning permission to roles

## Request

To be able to do this you should make a `POST` request to the `/roles/:id/permission` endpoint.
In the payload you should send an `array` of `objects` containing the id of the roles.

```json
{
    "data": [
        {
            "id": 10
        },
        {
            "id": 3
        },
        {
            "id": 4
        },
        {
            "id": 5
        }
    ]
}
```

This will then mass assign these permission to that role.

## Response

The response object will then return the count of how many roles it has inserted

```json
{
    "count": 4
}

```

# Updating role permissions

## Request

To be able to do this you should make a `PATCH` request to the `/roles/:id/permission` endpoint.
In the payload you should send an `array` of `objects` containing the id of the roles.


```json
{
    "data": [
        {
            "id": 10
        },
        {
            "id": 3
        },
        {
            "id": 4
        },
    ]
}
```

**NOTE: The difference between these 2 endpoints is that the `PATCH` REMOVES all the previous roles and assigns the new ones that have been given in the array**

## Response

The response object will then return the count of how many roles it has inserted

```json
{
    "count": 4
}

```