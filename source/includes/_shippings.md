# Shippings

## Create a Shipping data

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/shipping \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "price=10" \
     -d "weight=3" \
     -d "site_name=site_name" \
     -d "provider=provider" \
     -d "destination=destination" \
     -d "enabled=True"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping":
    {
        "id": "[id]",
        "price": 10,
        "weight": 3.0,
        "site_name": "site_name",
        "provider": "provider",
        "destination": "destination",
        "enabled": true
    }
}
```

This endpoint create Shipping data.

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/shipping`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
weight      | (required) | limite superior del rango
site_name   | (required) | nombre del sitio a la cual pertenece
provider    | (required) | nombre del proveedor de servicio
destination | (required) | nombre de la comuna a despachar
price       | (optional) | precio del despacho
enabled     | (optional) | indica si es visible en checkout




## Edit Shipping data

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/shipping/[id] \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "price=100" \
     -d "weight=6" \
     -d "provider=provider_A" \
     -d "destination=destination_A" \
     -d "enabled=False"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping":
    {
        "id": "[id]",
        "price": 100,
        "weight": 6.0,
        "provider": "provider_A",
        "destination": "destination_A",
        "enabled": false
    }
}
```

This endpoint edit Shipping data.

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/shipping/[id]`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
id          | (required) | identificador numerico unico para despacho
price       | (optional) | precio del despacho
weight      | (optional) | limite superior del rango
provider    | (optional) | nombre del proveedor de servicio
destination | (optional) | nombre de la comuna a despachar
enabled     | (optional) | indica si es visible en checkout



## Delete Shipping data

```shell
curl -XDELETE https://apibodegas.loadingplay.com/v1/shipping/[id] \
     -H 'Authorization: Bearer ACCESS_TOKEN'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping":
    {
        "id": "[id]",
        "price": 100,
        "weight": 6.0,
        "provider": "provider_A",
        "destination": "destination_A",
        "enabled": false
    }
}
```

This endpoint delete a Customer.

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/shipping/[id]`

### URL Parameters

Parameter | Default    | Description
--------- | ---------- | -----------
id        | (required) | identificador numerico unico para despacho




## Get a Provider list

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/shipping/provider \
     -d "site_name=site_name"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shippings": [
        {"provider": "provider"},
        {"provider": "provider_A"},
        ...
    ]
}
```

This endpoint get a provider list.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/shipping/provider`

### URL Parameters

Parameter | Default    | Description
--------- | ---------- | -----------
site_name | (required) | nombre del sitio a la cual pertenece




## Get Shipping data by provider

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/shipping/provider/[name] \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "site_name=site_name"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shippings": [
        {
            "id": "[id]",
            "price": 10,
            "weight": 3.0,
            "site_name": "site_name",
            "provider": "[name]",
            "destination": "destination",
            "enabled": true
        },
        ...
    ]
}
```

This endpoint get shipping data by provider.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/shipping/provider/[name]`

### URL Parameters

Parameter | Default    | Description
--------- | ---------- | -----------
name      | (required) | nombre del proveedor
site_name | (required) | nombre del sitio a la cual pertenece




## Get Shipping data by destination

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/shipping/provider/[name]/destination/[destination_name] \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "site_name=site_name"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shippings": [
        {
            "id": "[id]",
            "price": 10,
            "weight": 3.0,
            "site_name": "site_name",
            "provider": "[name]",
            "destination": "[destination_name]",
            "enabled": true
        },
        ...
    ]
}
```

This endpoint get shipping data by destination.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/shipping/provider/[name]/destination/[name]`

### URL Parameters

Parameter        | Default    | Description
---------------- | ---------- | -----------
name             | (required) | nombre del proveedor
destination_name | (required) | nombre del destino
site_name        | (required) | nombre del sitio a la cual pertenece




## Get Price by weight

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/shipping/price \
     -d "weight=2" \
     -d "site_name=site_name" \
     -d "provider=provider" \
     -d "destination=destination"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping": {
        "price": 10
    }
}
```

This endpoint get shipping data by destination.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/shipping/price`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
weight      | (required) | limite superior del rango
site_name   | (required) | nombre del sitio a la cual pertenece
provider    | (required) | nombre del proveedor de servicio
destination | (required) | nombre de la comuna a despachar




## Activate/Deactivate shipping town

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/shipping/enable \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "site_name=site_name" \
     -d "provider=provider" \
     -d "destination=destination" \
     -d "enabled=True"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shippings": [
        { "enabled": true },
        ...
    ]
}
```

This endpoint activate/deactivate town previously created in checkout with #create-a-shipping-data.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/shipping/enable`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
site_name   | (required) | nombre del sitio a la cual pertenece
provider    | (required) | nombre del proveedor de servicio
destination | (required) | nombre de la comuna a despachar
enabled     | (required) | indica si es visible en checkout
