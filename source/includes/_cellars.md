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

| Parameter   | Default    | Description                                   |
| ----------- | ---------- | --------------------------------------------- |
| name        | (required) | name of the cellar                            |
| descrìption | ""         | description of the cellar                     |
| for_sale    | False      | true indicate that cellar it's web            |
| reservation | False      | true indicate that cellar it's storage        |




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

| Argument    | Default    | Description                                                                                          |
| ----------- | ---------- | ---------------------------------------------------------------------------------------------------- |
| cellar_id   | (required) | unique identifier for cellar                                                                         |

### Query Parameters

| Parameter   | Default    | Description                                                                                          |
| ----------- | ---------- | ---------------------------------------------------------------------------------------------------- |
| name        | (optional) | name of the cellar                                                                                   |
| description | (optional) | description of the cellar                                                                            |
| for_sale    | (optional) | true if this cellar is enabled for web, the system will allow only one cellar as web                 |
| reservation | (optional) | true if this cellar is enabled for reservation, the system will allow only one cellar as reservation |




## List cellars

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar" \
     -H "Authorization: Bearer ACCESS_TOKEN"
     -d "page=1" \
     -d "items=10" \
     -d "search="
```

> The above command returns json with a list of cellars, including id:

```json
{
    "status": "success",
    "cellar": [
        {
            "id": "[cellar_id]",
            "name": "[cellar_name]",
            "site_name": "[site_name]"
        },
        ...
    ]
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar`

### URL Parameters

| Parameter | Default | Description                                        |
| --------- | ------- | -------------------------------------------------- |
| page      | (int)   | page number                                        |
| items     | (int)   | items per page                                     |
| search    | (str)   | use this if you want to search in cellar           |
| metadata  | (bool)  | true if you want to get metadata for the bdd query |


## List products in a cellar

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/cellar/[ID]/products" \
     -H "Authorization: Bearer ACCESS_TOKEN"
     -d "page=1" \
     -d "items=10" \
     -d "search=" \
     -d "metadata=true"
```

> The above command returns json with a list of products inside a cellar:

```json
{
    "metadata": {
        "records_filtered": 10,
        "total_records_count": 100
    },
    "status": "success",
    "products": [
        {
            "product_sku": "the sku",
            "balance_units": 10
        },
        ...
    ]
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/cellar/[ID]/products`

### URL Parameters

| Parameter | Default | Description                                        |
| --------- | ------- | -------------------------------------------------- |
| page      | (int)   | page number                                        |
| items     | (int)   | items per page                                     |
| search    | (str)   | use this if you want to filter by sku              |
| metadata  | (bool)  | true if you want to get metadata for the bdd query |


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

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| cellar_id | (required) | unique identifier for cellar    |
| sku       | (required) | unique ididentifier for variant |

## PUT Variant Stock in a Cellar

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]/stock \
    -d 'sku=producto_3' \
    -d 'quantity=1' \
    -d 'user_description=example_sistem'\
    -d 'operation=move_in'\
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

| Parameter        | Default    | Description                                                                                |
| ---------------- | ---------- | ------------------------------------------------------------------------------------------ |
| cellar_id        | (required) | unique identifier for cellar                                                               |
| sku              | (required) | unique ididentifier for variant                                                            |
| quantity         | 0          | quantity to send, can be negative                                                          |
| user_description | "API"      | user who execute the stock post                                                            |
| operation        | "move_in"  | the operation who repesent the stock adding (can be 'buy','sell', 'move_in' or 'move_out') |
