# PUT requests
You can use PUT requests to update an asset's `custom_properties` or `content` properties in Planning Analytics Workspace.

## Update an asset using the asset ID and type

> Example:

```html
http://localhost:1338/pacontent/v1/Assets(id='196bf85d-329c-40ec-bb43-5098176197dd',type='dashboard')?$expand=content
```

### Syntax
`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(id='<asset ID>',type='asset type')?$expand=content`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset ID | The ID for the asset.
Asset type | The type of asset.

### Body

> Example of the request body

```json
{
    "content": {
        "version": "7.0",
        "container": "C",
        "useSpec": [],
        "dataSource": [],
        "querySubject": [],
        "filter": [],
        "calculation": []
    },
    "custom_properties": {}
}
```

### Result

> Example of a response from a successful request

```json
{
    "path": "/shared/demo",
    "dynamic_properties": {
        "delete_link": "idvisualizations/c/v2/content/dashboard/297df01f-debf-401f-8d4e-67a7b3c7b01e/",
        "extended_info_link": "idvisualizations/c/v2/info/dashboard/297df01f-debf-401f-8d4e-67a7b3c7b01e/?view=extended_info",
        "thumbnail_link": "idvisualizations/c/v2/attachment/dashboard/297df01f-debf-401f-8d4e-67a7b3c7b01e/?name=thumbnail",
        "open_link": "gemini/board/297df01f-debf-401f-8d4e-67a7b3c7b01e/?embed=ba1"
    },
    "system_properties": {
        "used_date": "2020-05-12T20:24:41.356Z",
        "used_user_id": "5d39c9bbe4b0e222859a1452",
        "used_user_pretty_name": "Admin",
        "attachments": [],
        "created_user_pretty_name": "Admin",
        "permissions": [
            "list",
            "open",
            "write",
            "manage",
            "secure"
        ],
        "created_user_id": "5d39c9bbe4b0e222859a1452",
        "modified_user_pretty_name": "Admin",
        "modified_user_id": "5d39c9bbe4b0e222859a1452",
        "created_date": "2020-05-12T20:24:22.555Z",
        "modified_date": "2020-05-12T20:24:41.367Z"
    },
    "kind": "c#info",
    "name": "demo",
    "description": "",
    "id": "297df01f-debf-401f-8d4e-67a7b3c7b01e",
    "state": "valid",
    "custom_properties": {},
    "type": "dashboard",
    "version": 0
}
```

The asset is updated with the specified values.