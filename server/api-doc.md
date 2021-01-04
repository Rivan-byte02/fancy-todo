# Fancy Todo app

## RESTful endpoints

### POST /todos

> Post all todos

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
{
    "title": "<title to get insert into>",
    "description": "<description to get insert into>",
    "status": <false when first created>,
    "due_date": "<due date to insert into>"
}
```

_Response (201)_
```
{
    "id": <given by system>,
    "title": "<posted title>",
    "description": "<posted description>",
    "status": <false>,
    "due_date": "<posted due date>",
    "createdAt": "<2020-03-20T07:15:12.149Z>",
    "updatedAt": "<2020-03-20T07:15:12.149Z>"
}
```

_Response (400)_
```
{
    "message": "validation error"
}
```

_Response (500)_
```
{
    "message": "Internal Server Error"
}
```

### GET /todos

> Get all todos

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
not needed
```

_Response (200)_
```
[
    {
        "id": 1,
        "title": "<todo title>",
        "description": "<todo description>",
        "status": <todo status>,
        "due_date": "<todo due date>",
        "createdAt": "<2020-03-20T07:15:12.149Z>",
        "updatedAt": "<2020-03-20T07:15:12.149Z>"
    },
    {
        "id": 2,
        "title": "<todo title>",
        "description": "<todo description>",
        "status": <todo status>,
        "due_date": "<todo due date>",
        "createdAt": "<2020-03-20T07:15:12.149Z>",
        "updatedAt": "<2020-03-20T07:15:12.149Z>"  
    }
]
```

_Response (500)_
```
{
    "message": "Internal Server Error"
}
```

## GET /todos/:id

> Get todo by id

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
{
    "id": <todo id>
}
```

_Response (200)_
```
{
    "id": <todo id>,
    "title": "<todo title>",
    "description": "<todo description>",
    "status": <todo status>,
    "due_date": "<todo due date>",
    "createdAt": "<2020-03-20T07:15:12.149Z>",
    "updatedAt": "<2020-03-20T07:15:12.149Z>"
}
```

_Response (404)_
```
{
    "message": "error not found"
}
```

### PUT /todos/:id

> Update todo by id

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
{
    "title": "<todo title>",
    "description": "<todo description>",
    "status": <todo status>,
    "due_date": "<todo due date>"
}
```

_Response (200)_
```
{
    "id": <todo id>,
    "title": "<updated todo title>",
    "description": "<updated todo description>",
    "status": <updated todo status>,
    "due_date": "<updated todo due date>",
    "createdAt": "<2020-03-20T07:15:12.149Z>",
    "updatedAt": "<date the todo updated>"
}
```

_Response (400)_
```
{
    "message": "validation error"
}
```

_Response (404)_
```
{
    "message": "error not found"
}
```

_Response (500)_
```
{
    "message": "Internal server error"
}
```

### PATCH /todos/:id

> Update todo by id

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
{
    "status": <todo status>
}
```

_Response (200)_
```
{
    "id": <todo id>,
    "title": "<todo title>",
    "description": "<todo description>",
    "status": <updated todo status>,
    "due_date": "<todo due date>",
    "createdAt": "<2020-03-20T07:15:12.149Z>",
    "updatedAt": "<date the todo updated>"
}
```

_Response (400)_
```
{
    "message": "validation error"
}
```

_Response (404)_
```
{
    "message": "error not found"
}
```

_Response (500)_
```
{
    "message": "Internal server error"
}
```

### DELETE /todos/:id

_Request Header_
```
{
    "access_token": "<your access token>"
}
```

_Request Body_
```
{
    "id": <todo id>
}
```

_Response (200)_
```
{
    "message": "todo success to delete"
}
```

_Response (404)_
```
{
    "message": "error not found"
}
```

_Response (500)_
```
{
    "message": "Internal server error"
}
```