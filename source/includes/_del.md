# DEL requests

You can use DEL requests to delete an asset in Planning Analytics Workspace.

## Delete an asset by ID

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(id='0985d8bf-6fb2-42d8-a31d-5a312f43e18c',type='dashboard')
```

This DEL request locates and deletes an asset based on the asset ID and asset type.

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets('<asset ID>', type='<asset type>')`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset ID | The ID for the asset.
Asset type | The type of asset.

### Result

The asset with the provided asset ID and type is deleted from Planning Analytics Workspace.

## Delete an asset by path

> Example of the syntax:

```html
http://localhost:1338/pacontent/v1/Assets(path='%252Fshared%252Fdemo')
```

### Syntax

`http://<Planning Analytics Workspace server URL>:<port number>/pacontent/v1/Assets(path='<asset path>')`

Values | Description
---- | ------
Planning Analytics Workspace server URL | The URL for the Planning Analytics Workspace server that your asset is located in.
Port number | The port number used for your server URL.
Asset path | The path of the asset.


### Result

The asset located in the provided path is deleted from Planning Analytics Workspace.