# Variants

## Create a Variant

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/variant" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "variant_name=size" \
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns json with variant info, including id:

```json
{
    "status": "success",
    "variant": {
        "id": [id],
        "name": "size",
        "site_name": "test",
        "sku": "sku-test"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/variant`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
variant_name | (required) | name of the variant i.e: size, color
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Delete a Variant
```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/variant/[variant_name]" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns json:

```json
{
    "status": "success",
    "variant": {
        "id": [id],
        "name": [variant_name],
        "site_name": "test",
        "sku": "sku-test"
    }
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/variant/[variant_name]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
variant_name | (required) | name of the variant i.e: size, color
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Get variants for a product

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/variant" \
  -d "site_name=[site_name]" \
  -d "sku=[product_sku]"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "variants": [
        {
            "id": [ID],
            "name": "size",
            "site_name": "test",
            "sku": "sku-test"
        },
        {
            "id": [ID],
            "name": "color",
            "site_name": "test",
            "sku": "sku-test"
        },
        ...
    ]
}
```

This endpoint retrieves a list of variants for Site and SKU.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/variant`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Create a Value for a variant

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "namespace=[site_name]_[product_sku]" \
    -d "value=[new_value]"
```

> The above command returns json with variant info, including id:

```json
{
    "status": "success",
    "value": {
        "id": "[id]",
        "value":  "[value]",
        "variant_name": "[variant]",
        "namespace": "[namespace]"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value`

### URL Parameters

Parameter | Description
--------- | -----------
namespace | a namespace should be compound by [site\_name]\_[product\_sku]
variant_name | name of the variant i.e: size, color
value | value name i.e (s, m, l)




## Delete a Value for a Variant
```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value/[value_name]" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "namespace=[site_name]_[product_sku]"
```

> The above command returns json:

```json
{
    "statuts" : "success"
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value/[value_name]`

### URL Parameters

Parameter | Description
--------- | -----------
namespace | [site\_name]\_[product\_sku]




## Get Value list

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value" \
  -d "namespace=[site_name]_[product_sku]"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "values": {
        "variant_name": "[variant_name]",
        "values": [{
            "site_name": "me_NBK-SACO-NEGRA-C168",
            "id": 1,
            "value": "1",
            "variant_name": "talla"
        }]
    }
}
```

This endpoint retrieves a list of values for a specific namespace([site\_name]\_[product\_sku]).

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value`

### URL Parameters

Parameter | Description
--------- | -----------
namespace | [site\_name]\_[product\_sku]
variant_name | selected variant




## Get Combination list

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/variant/[sku]/combination" \
  -d "namespace=[site_name]"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "combination": [
        {"sku": "test-m-azul", "data": ""}
    ]
}
```

This endpoint retrieves a list of combinatios for a specific namespace([site\_name]) and
sku ([product\_sku]).

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/variant/[sku]/combination`

### URL Parameters

Parameter | Description
--------- | -----------
namespace | [site\_name]
sku | the product sku
