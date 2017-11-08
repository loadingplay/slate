# Config

## Get all Configs from a Syte Name

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/config \
            -d 'site_name=fm' \
            -d 'access_token=Bearer ACCESS_TOKEN'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "config": [
        {
            "name": "mod_conf_payment_methods",
            "value": "on"
        },
        {
            "name": "mod_users",
            "value": "on"
        },
        {
            "name": "shipping_id",
            "value": ""
        },
        {
            "name": "bullet_1",
            "value": "on"
        },
        {
            "name": "instagram",
            "value": ""
        },
        {
            "name": "bullet_3",
            "value": ""
        },
        {
            "name": "bullet_2",
            "value": "on"
        },
        {
            "name": "mod_orders",
            "value": "on"
        },
        {
            "name": "checkout_upon_delivery",
            "value": "on"
        },
        {
            "name": "pedido_despachado",
            "value": "family-market-confirmacion-pedido"
        },
        {
            "name": "price",
            "value": "on"
        },
        {
            "name": "analytics",
            "value": "UA-69991660-1"
        },
        ....
    ]
}
```

This endpoint retrieves all the config of a syte.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/Config`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
site_name | (required) | filter by site

## Get a Specific Config from a Syte Name

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/config \
    -d 'site_name=fm' \
    -d 'access_token=Bearer ACCESS_TOKEN' \
    -d 'name=CONFIG_NAME'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "config": [
        {
            "name": "mod_users",
            "value": "on"
        }
    ]
}
```

This endpoint retrieves a specific config.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/Config`

### URL Parameters

Parameter | Description
--------- | -----------
site_name | (required) filter by site
name | unique identifier for the config it can be a comma separated list, and return a comma separated list of configs

## Create a Config Element
```shell

curl -XPOST https://apibodegas.loadingplay.com/v1/config \
        -d 'site_name=fm' \
        -d 'name=' \
        -d 'value=' \
        -d 'access_token=Bearer ACCESS_TOKEN'
```

> The above command returns json with the new config info, including id:

```json
{
    "status": "success",
    "config": {
        "site_name": "fm",
        "name": [config_name],
        "value": [value]
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/Config`

### URL Parameters

Parameter | Description
--------- | -----------
site_name | (required) filter by site
name | unique identifier for the config 
value | value of the config, it can be 'on', '' or a String