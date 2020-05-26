> Example:

```json
{
    "type": "dashboard",
    "name": "example_name",
    "path": "/shared",
    "content": {
        "example_content": "content"
    },
    "custom_properties": {
        "score": 100
    }
}
```

The Planning Analytics Content Service API accepts and returns requests in JSON. You can use the following parameters when sending POST and PUT requests.

Parameter name | Description
---------- | ------- 
type | The asset type.
name | The asset name.
path | The asset path.
content | The `content` property of the asset that you want to add or modify. The `content` parameter can be expanded to reveal an array of nested parameters in an asset. You can add or modify the parameters in this array. Parameters in the `content` property may differ between asset types.
custom_properties | The `custom_properties` property of the asset that you want to add or modify. You can use `custom_properties` for any custom values that you would like to store in the asset.


# Supported OData query options

The Planning Analytics Content Services API supports several OData query options. These query options can be used to refine your requests.

## $expand

You can use `$expand` to expand a folder asset. If you have a folder asset and you want to read the children assets of that folder, `$expand` will return the children assets of that folder.

The `$expand` option can also be used if you want to view the contents of an asset, such as a dashboard.

For example, `http://localhost:1338/pacontent/v1/Assets('94d80e2b-8285-4926-9d37-08f5f32f9b68')?$expand=content` expands and returns the `content` property from the asset.

## $filter

You can use `$filter` with an operator to filter the retrieved JSON properties. `$filter` can be used only with `$expand` for expanded assets.

For example, `$filter=name eq finance` returns only assets with `finance` in the `name` property.

`http://localhost:1338/pacontent/v1/Assets(path='%252fshared%252fdemo')?$expand=Assets($expand=content;$filter=name eq 'demo')` filters the expanded content based on if the asset contains a `name` property that is equal to the `demo` value.

## $select

You can use `$select` to select an asset with a certain property in your requests. The `$select` option can be used with `$expand` and in the URL query.

For example, `$select=name` returns only assets with the `name` property.

## $top

You can use `$top` to define the number of assets that you want returned, when returning an array.

For example, `$top=10` returns the first 10 assets in an array.

## $skip

You can use `$skip` to define the number of assets to skip when an array of assets is returned from within a folder.

For example, `$skip=3` skips the first 3 assets in an array.


## $orderby

You can use `$orderby` to define how you want your assets to be ordered when an array is returned.

For example, `$orderby=name` orders the returned assets by the `name` property and alphabetically.

## Operators

The following are operators that you can use with the `$filter` and `$select` options:

Operator | Description
----| -----
eq | The `eq` operator returns true if the left operand is equal to the right operand, otherwise it returns false.
ne | The `ne` operator returns true if the left operand is not equal to the right operand, otherwise it returns false.
gt | The `gt` operator returns true if the left operand is greater than the right operand, otherwise it returns false.
ge | The `ge` operator returns true if the left operand is greater than or equal to the right operand, otherwise it returns false.
lt | The `lt` operator returns true if the left operand is less than the right operand, otherwise it returns false.
le | The `le` operator returns true if the left operand is less than or equal to the right operand, otherwise it returns false.
and | The `and` operator returns true if both the left and right operands evaluate to true, otherwise it returns false.

<!--or | The `or` operator returns false if both the left and right operands both evaluate to false, otherwise it returns true.
not | The `not` operator returns true if the operand returns false, otherwise it returns false.
has | The `has` operator returns true if the right operand is an enumeration value whose flag(s) are set on the left operand.
in | The `in` operator returns true if the left operand is a member of the right operand. The right operand MUST be either a comma-separated list of primitive values, enclosed in parentheses, or a single expression that resolves to a collection. -->
