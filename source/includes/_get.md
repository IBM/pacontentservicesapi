# GET requests
You can use GET requests to retrieve metadata about an asset in Planning Analytics Workspace.

## Get asset from an ID

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')
```

This GET request uses the asset ID to retrieve and return the metadata from the asset from the server.

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets('<asset ID>')`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset ID | The ID for the asset.

### Result

> Example of the metadata retrieved

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
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
        "delete_link": "idvisualizations/r/v2/content/shared/demo/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/demo/?name=thumbnail"
    },
    "custom_properties": {}
}
```
The metadata for the asset is returned.

<aside class="note">
Note: If you want the `content` that is stored inside of the asset, you need to include the OData $expand query parameter.
</aside>

## Get asset and expand content from an ID

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')?$expand=content
```

This GET request uses the asset ID to retrieve the asset metadata and also the content of the asset.

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets('<asset ID>')?$expand=content`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset ID | The ID for the asset.

### Result

> Example of the asset metadata and content retrieved

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
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
        "delete_link": "idvisualizations/r/v2/content/shared/demo/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/demo/?name=thumbnail"
    },
    "custom_properties": {},
    "content": {
        "container": "C",
        "filter": [],
        "calculation": [],
        "querySubject": [],
        "version": "6.0",
        "dataSource": [],
        "useSpec": []
    }
}
```

## Get asset using a path

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252fshared%252fdemo')
```

This GET requests uses the path of the asset to retrieve asset data. Using the path is useful if you're unsure about what the ID of the asset is. 

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<path of the asset>')`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset ID | The ID for the asset.
Asset path | The path of asset.

<aside class="note">
Note: The path of your asset must be URL encoded twice.
</aside>

### Result

> Example of the asset retrieved

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
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
        "used_date": "2020-05-12T19:15:36.401Z",
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
        "delete_link": "idvisualizations/r/v2/content/shared/demo/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/demo/?name=thumbnail"
    },
    "custom_properties": {}
}
```

The asset is retrieved using the path of the asset.

## Get asset and content using a path

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='shared%252Fdemo')?$expand=content
```

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<path of the asset>')?$expand=content`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset path | The path of asset.

<aside class="note">
Note: The path of your asset must be URL encoded twice.
</aside>

### Result

> Example of the asset metadata and content retrieved

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
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
        "used_date": "2020-05-12T19:15:36.401Z",
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
        "delete_link": "idvisualizations/r/v2/content/shared/demo/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/demo/?name=thumbnail"
    },
    "custom_properties": {},
    "content": {
        "container": "C",
        "filter": [],
        "calculation": [],
        "querySubject": [],
        "version": "6.0",
        "dataSource": [],
        "useSpec": []
    }
}
```
The asset metadata and content is retrieved using the asset path.

## Get assets of a folder

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252fshared')/Assets
```

This GET request retrieves the children assets of a folder.

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<folder path>')/Assets`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Folder path | The path of the folder where your assets are located in.

<aside class="note">
Note: The path of your folder must be URL encoded twice.
</aside>

### Result

> Example of the assets within a folder being retrieved

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets('/shared')/Assets",
    "value": [
       {
            "@odata.id": "http://localhost:1338/v1/Assets('3edf76f6-7b09-40cf-a467-47b8f55eec15')",
            "@odata.editLink": "http://localhost:1338/v1/Assets('3edf76f6-7b09-40cf-a467-47b8f55eec15')",
            "id": "3edf76f6-7b09-40cf-a467-47b8f55eec15",
            "description": "",
            "name": "revenue_2020",
            "path": "/shared/revenue_2020",
            "type": "dashboard",
            "kind": "c#info",
            "state": "valid",
            "version": 0,
            "system_properties": {
                "created_date": "2019-09-19T16:33:12.318Z",
                "created_user_id": "5d39c9bbe4b0e222859a1452",
                "created_user_pretty_name": "Admin",
                "modified_date": "2019-09-19T16:33:12.318Z",
                "modified_user_id": "5d39c9bbe4b0e222859a1452",
                "modified_user_pretty_name": "Admin",
                "used_date": "2020-04-15T13:23:15.889Z",
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
                "delete_link": "idvisualizations/r/v2/content/shared/yy-empty/",
                "thumbnail_link": "idvisualizations/r/v2/attachment/shared/yy-empty/?name=thumbnail"
            },
            "custom_properties": {}
        },
        {
            "@odata.id": "http://localhost:1338/v1/Assets('1773db5b-972a-424f-a9a5-be49af5ec137')",
            "@odata.editLink": "http://localhost:1338/v1/Assets('1773db5b-972a-424f-a9a5-be49af5ec137')",
            "id": "1773db5b-972a-424f-a9a5-be49af5ec137",
            "description": "",
            "name": "finance_2020",
            "path": "/shared/finance_2020",
            "type": "dashboard",
            "kind": "c#info",
            "state": "valid",
            "version": 0,
            "system_properties": {
                "created_date": "2019-08-08T17:37:31.050Z",
                "created_user_id": "5d39c9bbe4b0e222859a1452",
                "created_user_pretty_name": "Admin",
                "modified_date": "2019-08-08T17:37:31.050Z",
                "modified_user_id": "5d39c9bbe4b0e222859a1452",
                "modified_user_pretty_name": "Admin",
                "used_date": "2020-04-15T14:50:01.768Z",
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
                "delete_link": "idvisualizations/r/v2/content/shared/yy-plansample/",
                "thumbnail_link": "idvisualizations/r/v2/attachment/shared/yy-plansample/?name=thumbnail"
            },
            "custom_properties": {}
        },
        {
            "@odata.id": "http://localhost:1338/v1/Assets('f6b71c40-ca1b-4a38-b167-8f8fa1359949')",
            "@odata.editLink": "localhost:1338/v1/Assets('f6b71c40-ca1b-4a38-b167-8f8fa1359949')",
            "id": "f6b71c40-ca1b-4a38-b167-8f8fa1359949",
            "description": "",
            "name": "finance_2019",
            "path": "/shared/finance_2019",
            "type": "dashboard",
            "kind": "c#info",
            "state": "valid",
            "version": 0,
            "system_properties": {
                "created_date": "2020-04-08T20:48:10.654Z",
                "created_user_id": "5d39c9bbe4b0e222859a1452",
                "created_user_pretty_name": "Admin",
                "modified_date": "2020-04-08T20:48:10.654Z",
                "modified_user_id": "5d39c9bbe4b0e222859a1452",
                "modified_user_pretty_name": "Admin",
                "used_date": "2020-05-12T14:55:01.980Z",
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
                "delete_link": "idvisualizations/r/v2/content/shared/%EB%A6%AC%EB%84%A4%EC%83%A4%EB%AF%BC%EA%B8%B0%EC%88%98/",
                "thumbnail_link": "idvisualizations/r/v2/attachment/shared/%EB%A6%AC%EB%84%A4%EC%83%A4%EB%AF%BC%EA%B8%B0%EC%88%98/?name=thumbnail"
            },
            "custom_properties": {}
        }
    ]
}
```
Children assets of the folder are listed in an array under `value`.

## Get and filter children assets of a folder

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252fshared')?$expand=Assets($expand=content;$filter=name eq 'demo')
```

This GET request retrieves and filters the children assets of a folder.

### Syntax

The following is the syntax for retrieving an asset from the asset ID:

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<folder path>')?$expand=Assets($expand=content;$filter=<filter type> <filter condition> '<filter value>')`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Folder path | The path of the folder where your assets are located in.
Filter type | The type of data that you want to filter the children by.
Filter condition | Set to `eq` to filter the children based on the `equals` filter condition.
Filter value | The value that you want to filter the children on.

<aside class="note">
Note: The path of your folder must be URL encoded twice.
</aside>

### Result

> Example of a response from a successful request

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "id": "c2c24d17-8abb-478e-a2e5-c2853cdae81a",
    "description": "",
    "name": "shared",
    "path": "/shared",
    "type": "folder",
    "kind": "c#info",
    "state": "valid",
    "version": 0,
    "system_properties": {
        "created_date": "2019-07-25T15:24:42.304Z",
        "created_user_id": null,
        "created_user_pretty_name": null,
        "modified_date": "2019-07-25T15:24:42.304Z",
        "modified_user_id": null,
        "modified_user_pretty_name": null,
        "used_date": "2019-07-25T15:24:42.304Z",
        "used_user_id": null,
        "used_user_pretty_name": null,
        "permissions": [
            "list",
            "open",
            "write",
            "manage",
            "secure"
        ]
    },
    "dynamic_properties": {
        "delete_link": "idvisualizations/r/v2/content/shared/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/?name=thumbnail"
    },
    "custom_properties": {
        "NATURE": "SYSTEM",
        "WA_PRO_READY": "true"
    },
    "Assets": [
        {
            "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
            "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
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
                "used_date": "2020-05-12T19:34:33.742Z",
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
                "delete_link": "idvisualizations/r/v2/content/shared/demo/",
                "thumbnail_link": "idvisualizations/r/v2/attachment/shared/demo/?name=thumbnail"
            },
            "custom_properties": {},
            "content": {
                "container": "C",
                "filter": [],
                "calculation": [],
                "querySubject": [],
                "version": "6.0",
                "dataSource": [],
                "useSpec": []
            }
        }
    ]
}
```
## Get, filter, and select assets

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252Fshared')?$expand=Assets($select=name;$filter=name eq 'demo')&$select=name
```
This GET requests retrieves and expands the shared folder assets. The request then filters the children assets and returns the specified `$select` value from children assets matching the specified `$filter` value. A `$select` option is also applied to the shared folder and returns the specified `$select` value for the folder.


### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<folder path>')?$expand=Assets($select=<select type>;$filter=<filter type> <filter condition> '<filter value>')&$select=<select type>`

* The `$expand=Assets` option expands the assets of the shared folder.
* The `$select=id` option returns only the `id` value of the expanded children assets.
* The `$filter=name` option returns only children assets with a `name` value of `demo`.
* The `$select=name eq 'demo'` option returns only the `name` value for the shared folder.



Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Folder path | The path of the folder where your assets are located in.
Filter type | The type of data that you want to filter the children by.
Filter condition | Set to `eq` to filter the children based on the `equals` filter condition.
Filter value | The value that you want to filter the children on.
Select type | The type of data that you want to select by.


<aside class="note">
Note: The path of your folder must be URL encoded twice.
</aside>

### Result

> Example of a response from a successful request

```json
{
    "@odata.context": "http://localhost.fyre.ibm.com:1338/v1/$metadata#Assets(name)/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "@odata.editLink": "http://localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "name": "shared",
    "Assets": [
        {
            "name": "demo"
        }
    ]
}
```

## Get, filter, select, and expand assets

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252Fshared')?$expand=Assets($select=id,type,path;$expand=content;$filter=name eq 'demo')
```
This GET requests retrieves and expands the shared folder assets. The request then filters the children assets and returns the specified `$select` value from children assets matching the specified `$filter` value. A `$select` option is also applied to the shared folder and returns the specified `$select` value for the folder.

Unlike the previous example, this request also expands the content of the returned children assets by using the `$expand=content` option.


### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<folder path>')?$expand=Assets($select=<select type>;$filter=<filter type> <filter condition> '<filter value>')&$select=<select type>`

* The `$expand=Assets` option expands the assets of the shared folder.
* The `$select=id` option returns only the `id` value of the expanded children assets.
* The `$filter=name` option returns only children assets with a `name` value of `demo`.
* The `$select=name eq 'demo'` option returns only the `name` value for the shared folder.



Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Folder path | The path of the folder where your assets are located in.
Filter type | The type of data that you want to filter the children by.
Filter condition | Set to `eq` to filter the children based on the `equals` filter condition.
Filter value | The value that you want to filter the children on.
Select type | The type of data that you want to select by.


<aside class="note">
Note: The path of your folder must be URL encoded twice.
</aside>

### Result

> Example of a response from a successful request

```json
{
    "@odata.context": "http://localhost:1338/v1/$metadata#Assets/$entity",
    "@odata.id": "http://localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "@odata.editLink": "localhost:1338/v1/Assets('c2c24d17-8abb-478e-a2e5-c2853cdae81a')",
    "id": "c2c24d17-8abb-478e-a2e5-c2853cdae81a",
    "description": "",
    "name": "shared",
    "path": "/shared",
    "type": "folder",
    "kind": "c#info",
    "state": "valid",
    "version": 0,
    "system_properties": {
        "created_date": "2019-07-25T15:24:42.304Z",
        "created_user_id": null,
        "created_user_pretty_name": null,
        "modified_date": "2019-07-25T15:24:42.304Z",
        "modified_user_id": null,
        "modified_user_pretty_name": null,
        "used_date": "2019-07-25T15:24:42.304Z",
        "used_user_id": null,
        "used_user_pretty_name": null,
        "permissions": [
            "list",
            "open",
            "write",
            "manage",
            "secure"
        ]
    },
    "dynamic_properties": {
        "delete_link": "idvisualizations/r/v2/content/shared/",
        "thumbnail_link": "idvisualizations/r/v2/attachment/shared/?name=thumbnail"
    },
    "custom_properties": {
        "NATURE": "SYSTEM",
        "WA_PRO_READY": "true"
    },
    "Assets": [
        {
            "@odata.id": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
            "@odata.editLink": "http://localhost:1338/v1/Assets('0985d8bf-6fb2-42d8-a31d-5a312f43e18c')",
            "id": "0985d8bf-6fb2-42d8-a31d-5a312f43e18c",
            "path": "/shared/demo",
            "type": "dashboard",
            "content": {
                "container": "C",
                "filter": [],
                "calculation": [],
                "querySubject": [],
                "version": "6.0",
                "dataSource": [],
                "useSpec": []
            }
        }
    ]
}
```