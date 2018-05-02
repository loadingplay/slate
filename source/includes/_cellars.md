# Cellars

## Create a cellar

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/cellar" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "name=name" \
     -d "site_name=test"
```

> The above command returns json with cellar info, including id:

```json
{
    "status": "success",
    "cellar": {
        "id": "[cellar_id]",
        "name": "[cellar_name]",
        "site_name": "[site_name]"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/cellar`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
name         | (required) | name of the cellar
site_name    | (required) | name of the site where cellar will be created




## Delete a cellar

```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json:

```json
{
    "status": "success",
    "cellar": "[cellar_id]"
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
cellar_id | (required) | unique identifier for cellar

## Edit a cellar

```shell
curl -XPUT "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "name=[new_name]" \
     -d "description=[new_description]" \
     -d "for_sale=[true|false]" \
     -d "reservation=[true|false]"
```

> The above command returns json:

```json
{
    "status": "success",
    "cellar": {
        "id": "[id]",
        "name": "[name]",
        "description": "[description]",
        "for_sale": "[for_sale]",
        "reservation": "[reservation]"
    }
}
```

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
cellar_id | (required) | unique identifier for cellar
name | (optional) | name of the cellar
description | (optional) | description of the cellar
for_sale | (optional) | true if this cellar is enabled for web, the system will allow only one cellar as web
reservation | (optional) | true if this cellar is enabled for reservation, the system will allow only one cellar as reservation

## Get Variant Stock in a Cellar

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock \
            -d 'sku=producto_3' \
            -H 'Authorization: Bearer ACCESS_TOKEN'
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "stock": {
        "sku": "producto_3",
        "total": 4
    }
}
```

This endpoint retrieves the respective stock in cellar of sended variant.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
cellar_id | (required) | unique identifier for cellar
sku       | (required) | unique ididentifier for variant

## PUT Variant Stock in a Cellar

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock \
            -d 'sku=producto_3' \
            -d 'quantity=1' \
            -d 'user_description=example_sistem'\
            -H 'Authorization: Bearer ACCESS_TOKEN'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "stock": {
        "sku": "producto_3",
        "user_description": "example_sistem",
        "operation": "move_in",
        "total": 5
    }
}
```

This endpoint retrieves the respective result of adding stock to sendend vairant in cellar.

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
cellar_id | (required) | unique identifier for cellar
sku       | (required) | unique ididentifier for variant
quantity  | 0 | quantity to send, can be negative
user_description       | "API" | user who execute the stock post
operation       | "move_in" | the operation who repesent the stock adding (can be 'buy','sell', 'move_in' or 'move_out')