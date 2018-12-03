# Variants

## Create a Variant

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/variant" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "variant_name=size" \
     -d "sku=sku-test" \
     -d "separator=-"
```

> The above command returns json with variant info, including id:

```json
{
    "status": "success",
    "variant": {
        "id": "[id]",
        "name": "size",
        "separator": "-",
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
sku          | (required) | product sku
separator    | "-"        | string simbol between sku and variant



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
        "id": "[id]",
        "name": "[variant_name]",
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
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "variants": [
        {
            "id": "[id]",
            "name": "size",
            "site_name": "test",
            "sku": "sku-test"
        },
        {
            "id": "[id]",
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
     -d "value=rojo" \
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns json with variant info, including id:

```json
{
    "status": "success",
    "value": {
        "id": "[id]",
        "variant_name": "[variant_name]",
        "value": "rojo",
        "site_name": "test",
        "sku": "sku-test"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
variant_name | (required) | name of the variant i.e: size, color
value        | (required) | value name i.e (s, m, l)
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Delete a Value for a Variant
```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value/[value]" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns json:

```json
{
    "status" : "success"
    "value": {
        "id": "[id]",
        "variant_name": "[variant_name]",
        "value": "[value]",
        "site_name": "test",
        "sku": "sku-test"
    }
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value/[value]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
variant_name | (required) | name of the variant i.e: size, color
value        | (required) | value name i.e (s, m, l)
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Get Value list

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value" \
     -d "site_name=test" \
     -d "sku=sku-test"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "values": {
        "variant_name": "[variant_name]",
        "values": [
            "35",
            "36",
            "37"
        ]
    }
}
```

This endpoint retrieves a list of values for site and sku.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/variant/[variant_name]/value`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
variant_name | (required) | selected variant
site_name    | (required) | name of the site where variant
sku          | (required) | product sku




## Get Combination list

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/variant/[sku]/combination" \
     -d "site_name=test"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "combination": [
        {
            "sku": "test-m-azul",
            "data": ""
        },
        {
            "sku": "test-m-azul",
            "data": ""
        },
        ...
    ]
}
```

This endpoint retrieves a list of combinations for site and sku.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/variant/[sku]/combination`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
sku          | (required) | product sku
site_name    | (required) | name of the site where variant
