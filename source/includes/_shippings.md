# Shippings

## Create a Shipping data

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/shipping \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "price=10" \
     -d "weight=3" \
     -d "site_name=site_name" \
     -d "provider=provider" \
     -d "destination=destination"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping":
    {
        "id": "[id]",
        "price": 10,
        "weight": 3,
        "site_name": "site_name",
        "provider": "provider",
        "destination": "destination"
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




## Edit Shipping data

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/shipping/[id] \
     -H 'Authorization: Bearer ACCESS_TOKEN' \
     -d "price=100" \
     -d "weight=6" \
     -d "provider=provider_A" \
     -d "destination=destination_A"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "shipping":
    {
        "id": "[id]",
        "price": 100,
        "weight": 6,
        "provider": "provider_A",
        "destination": "destination_A"
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
        "weight": 6,
        "provider": "provider_A",
        "destination": "destination_A"
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
