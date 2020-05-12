# POST requests
You can use POST requests to send data to the Planning Analytics server and create assets in Planning Analytics Workspace.

## Creating a folder

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets
```
You can use a POST request to create a new folder in a path that you define.

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.

### Body

> Example of the JSON request body

```
{
    "type": "folder",
    "path": "/shared",
    "name": "demo"
}
```

In this example, the request is using the following keys:

Key name | Description
---------| -----------
type | The type of asset that you want to create.
path | The path where you want your asset to be created in.
name | The name that you want to give your asset.

### Result

> Example of a response from a successful request

```json
{
    "@odata.context": "http://harmonydev21.fyre.ibm.com:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://harmonydev21.fyre.ibm.com:1338/v1/Assets('46aabf88-bdf2-4b1d-a150-00e31ef804ea')",
    "@odata.editLink": "http://harmonydev21.fyre.ibm.com:1338/v1/Assets('46aabf88-bdf2-4b1d-a150-00e31ef804ea')",
    "id": "46aabf88-bdf2-4b1d-a150-00e31ef804ea",
    "description": "",
    "name": "demo",
    "path": "/shared/demo",
    "type": "folder",
    "kind": "c#info",
    "state": "valid",
    "version": 0,
    "system_properties": {
        "created_date": "2020-05-12T18:54:40.472Z",
        "created_user_id": "5d39c9bbe4b0e222859a1452",
        "created_user_pretty_name": "Admin",
        "modified_date": "2020-05-12T18:54:40.472Z",
        "modified_user_id": "5d39c9bbe4b0e222859a1452",
        "modified_user_pretty_name": "Admin",
        "used_date": "2020-05-12T18:54:40.472Z",
        "used_user_id": "5d39c9bbe4b0e222859a1452",
        "used_user_pretty_name": "Admin",
        "permissions": [
            "list",
            "open",
            "write",
            "manage",
            "secure"
        ]
    },
    "dynamic_properties": {
        "delete_link": "idvisualizations/c/v2/content/folder/46aabf88-bdf2-4b1d-a150-00e31ef804ea/",
        "thumbnail_link": "idvisualizations/c/v2/attachment/folder/46aabf88-bdf2-4b1d-a150-00e31ef804ea/?name=thumbnail"
    },
    "custom_properties": {}
}
```

A new folder is created.

## Creating a dashboard

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets
```
You can use a POST request to create a new dashboard in a path that you define. 

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets`

### Body

> Example of the JSON request body

```json
{
    "type": "dashboard",
    "name": "demo",
    "path": "/shared",
    "content": {
        "version": "6.0",
        "container": "C",
        "useSpec": [],
        "dataSource": [],
        "querySubject": [],
        "filter": [],
        "calculation": []
    }
}
```

In this example, the request is using the following keys:

Key name | Description
---------| -----------
type | The type of asset that you want to create.
path | The path where you want your asset to be created in.
name | The name that you want to give your asset.
content | The specifications for the asset that you are creating.

<aside class="note">
Note: The `content` key and values are required to create a dashboard.
</aside>

### Result

> Example of a response from a successful request

```json
{
    "@odata.context": "http://harmonydev21.fyre.ibm.com:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://harmonydev21.fyre.ibm.com:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "@odata.editLink": "http://harmonydev21.fyre.ibm.com:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "id": "0985d8bf-6fb2-42d8-a31d-5a312f43e18c",
    "description": "",
    "name": "demo",
    "path": "/shared/demo",
    "type": "dashboard",
    "kind": "c#info",
    "state": "valid",
    "version": 0,
    "system_properties": {
        "created_date": "2020-05-12T19:02:37.414Z",
        "created_user_id": "5d39c9bbe4b0e222859a1452",
        "created_user_pretty_name": "Admin",
        "modified_date": "2020-05-12T19:02:37.414Z",
        "modified_user_id": "5d39c9bbe4b0e222859a1452",
        "modified_user_pretty_name": "Admin",
        "used_date": "2020-05-12T19:02:37.414Z",
        "used_user_id": "5d39c9bbe4b0e222859a1452",
        "used_user_pretty_name": "Admin",
        "permissions": [
            "list",
            "open",
            "write",
            "manage",
            "secure"
        ]
    },
    "dynamic_properties": {
        "delete_link": "idvisualizations/c/v2/content/dashboard/0985d8bf-6fb2-42d8-a31d-5a312f43e18c/",
        "thumbnail_link": "idvisualizations/c/v2/attachment/dashboard/0985d8bf-6fb2-42d8-a31d-5a312f43e18c/?name=thumbnail"
    },
    "custom_properties": {}
}
```

A new dashboard is created.

