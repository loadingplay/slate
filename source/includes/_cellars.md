# Cellars

## Create a cellar

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/cellar" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "name=name"
```

> The above command returns json with cellar info, including id:

```json
{  
    "status": "success",
    "cellar": {  
        "site_name": "baymax",
        "description": "",
        "for_sale": false,
        "deleted": false,
        "reservation": false,
        "id": 171,
        "name": "name"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/cellar`

### Query Parameters

| Parameter   | Default    | Description                            |
| ----------- | ---------- | -------------------------------------- |
| name        | (required) | name of the cellar                     |
| descrìption | ""         | description of the cellar              |
| for_sale    | False      | true indicate that cellar it's web     |
| reservation | False      | true indicate that cellar it's storage |




## Get a cellar

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json:

```json
{
    "status": "success",
    "cellar": {
        "site_name": "baymax",
        "description": "",
        "for_sale": false,
        "deleted": true,
        "reservation": false,
        "id": 171,
        "name": "name"
    }
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Arguments

| Argument  | Default    | Description                  |
| --------- | ---------- | ---------------------------- |
| cellar_id | (required) | unique identifier for cellar |




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
        "reservation": [true|false],
        "for_sale": [true|false],
        "description": "[new_description]",
        "id": "[id]",
        "name": "[new_name]"
    }
}
```

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Arguments

| Argument    | Default    | Description                  |
| ----------- | ---------- |----------------------------- |
| cellar_id   | (required) | unique identifier for cellar |

### Query Parameters

| Parameter   | Default    | Description                                                                                          |
| ----------- | ---------- | ---------------------------------------------------------------------------------------------------- |
| name        | (optional) | name of the cellar                                                                                   |
| description | (optional) | description of the cellar                                                                            |
| for_sale    | (optional) | true if this cellar is enabled for web, the system will allow only one cellar as web                 |
| reservation | (optional) | true if this cellar is enabled for reservation, the system will allow only one cellar as reservation |




## Delete a cellar

```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json:

```json
{  
    "status": "success",
    "cellar": {  
        "site_name": "baymax",
        "description": "",
        "for_sale": false,
        "deleted": true,
        "reservation": false,
        "id": 171,
        "name": "name"
    }
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Arguments

| Argument  | Default    | Description                  |
| --------- | ---------- | ---------------------------- |
| cellar_id | (required) | unique identifier for cellar |




## List cellars

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar" \
     -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json with a list of cellars, including id:

```json
{
    "status": "success",
    "cellars": [
        {
            "site_name": "baymax",
            "description": "",
            "deleted": false,
            "for_sale": false,
            "reservation": true,
            "id": 112,
            "name": "reserva"
        },
        ...
    ]
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar`




## List products in a cellar

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar/[ID]/products" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "page=1" \
     -d "items=10" \
     -d "search=" \
     -d "metadata=true"
```

> The above command returns json with a list of products inside a cellar:

```json
{  
    "status": "success",
    "products": [  
        {  
           "product_sku": "aaaaa",
           "in_stock": false,
           "balance_units": -12
        },
        ...
    ],
    "metadata": {  
        "total_records": 5,
        "records_filtered": 5
    }
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/products`

### URL Arguments

| Argument  | Default    | Description                  |
| --------- | ---------- | ---------------------------- |
| cellar_id | (required) | unique identifier for cellar |

### Query Parameters

| Parameter | Default       | Description                                        |
| --------- | ------------- | -------------------------------------------------- |
| page      | 0             | page number                                        |
| items     | 10            | items per page                                     |
| metadata  | "false"       | true if you want to get metadata for the bdd query |
| search    | ""            | use this if you want to filter by sku              |
| column    | "product_sku" | column for sorting items                           |
| order     | "ASC"         | type of orden DESC or ASC                          |




## Get Variant Stock in a Cellar

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock" \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d 'sku=producto_3'
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

### URL Arguments

| Argument  | Default    | Description                  |
| --------- | ---------- | ---------------------------- |
| cellar_id | (required) | unique identifier for cellar |

### Query Parameters

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| sku       | (required) | unique ididentifier for variant |




## PUT Variant Stock in a Cellar

```shell
curl -XPUT "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock" \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d 'sku=producto_3' \
    -d 'quantity=1' \
    -d 'user_description=example_sistem' \
    -d 'operation=mov_in'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "stock": {
        "sku": "producto_3",
        "operation": "mov_in",
        "total": 5,
        "user_description": "example_sistem"
    }
}
```

This endpoint retrieves the respective result of adding stock to sendend vairant in cellar.

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock`

### URL Arguments

| Argument  | Default    | Description                  |
| --------- | ---------- | ---------------------------- |
| cellar_id | (required) | unique identifier for cellar |

### Query Parameters

| Parameter        | Default    | Description                                                                                |
| ---------------- | ---------- | ------------------------------------------------------------------------------------------ |
| sku              | (required) | unique ididentifier for variant                                                            |
| quantity         | 0          | quantity to send, can be negative                                                          |
| user_description | "API"      | user who execute the stock post                                                            |
| operation        | "mov_in"   | the operation who repesent the stock adding (can be 'buy','sell', 'mov_in' or 'mov_out')   |
