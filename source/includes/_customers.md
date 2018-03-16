# Customers

## Add a Customer

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/customer \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d "rut=rut" \
    -d "name=nombre" \
    -d "last_name=apellido" \
    -d "telephone=123456789" \
    -d "email=test@loadingplay.com" \
    -d "customer_type=persona" \
    -d "site_name=test"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "customer":
    {
        "id": [ID],
        "rut": "rut",
        "name": "nombre",
        "last_name": "apellido",
        "telephone": "123456789",
        "email": "test@loadingplay.com",
        "type": "persona",
        "deleted": false,
        "site_name": "test"
    }
}
```

This endpoint add a Customer.

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/customer`

### URL Parameters

Parameter     | Default    | Description
------------- | ---------- | -----------
email         | (required) | email con el cual se registra customer
site_name     | (required) | nombre del sitio del cual pertenece customer
rut           | (optional) | rut del customer
name          | (optional) | nombre del customer
last_name     | (optional) | apellido del customer
telephone     | (optional) | telefono del customer
email         | (optional) | email del customer
customer_type | (optional) | tipo de customer, por ejemplo: "persona", "empresa", etc
site_name     | (optional) | nombre de sitio del cual pertenece customer 




## Get a Customer

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/customer/[ID] \
    -H 'Authorization: Bearer ACCESS_TOKEN'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "customer":
    {
        "id": [ID],
        "rut": "rut",
        "name": "nombre",
        "last_name": "apellido",
        "telephone": "123456789",
        "email": "test@loadingplay.com",
        "type": "persona",
        "deleted": false,
        "site_name": "test",
        "registration_date": [REGISTRATION_DATE],
        "first_view": [FIRST_VIEW],
        "last_view": [LAST_VIEW]
    }
}
```

This endpoint retrieves a Customer.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/customer/CUSTOMER_ID`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
CUSTOMER_ID | (required) | identificador unico para customer




## Edit a Customer

```shell
curl -XPUT https://apibodegas.loadingplay.com/v1/customer/CUSTOMER_ID \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d "name=nombre1" \
    -d "last_name=apeliido1" \
    -d "telephone=987654321" \
    -d "email=test1@loadingplay.com" \
    -d "first_view=2010-03-15T16:52:43.662397" \
    -d "last_view=2011-03-15T16:52:43.662397"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "customer": 
    {
        "id": [ID],
        "name": "nombre1",
        "last_name": "apeliido1",
        "telephone": "987654321",
        "email": "test1@loadingplay.com"
        "deleted": false,
        "first_view": "2010-03-15T16:52:43.662397",
        "last_view": "2011-03-15T16:52:43.662397",
    }
}
```

This endpoint edit a Customer.

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/customer/CUSTOMER_ID`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
CUSTOMER_ID | (required) | identificador unico para customer
name        | (optional) | nombre del customer
last_name   | (optional) | apellido del customer
telephone   | (optional) | telefono del customer
email       | (optional) | email del customer
site_name   | (optional) | nombre de sitio del cual pertenece customer 
first_view  | (optional) | fecha en que realiza la primera compra
last_view   | (optional) | fecha en que se realiza la ultima compra




## Remove a Customer

```shell
curl -XDELETE https://apibodegas.loadingplay.com/v1/customer/CUSTOMER_ID \
    -H 'Authorization: Bearer ACCESS_TOKEN'
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "customer":
    {
        "id": [ID],
        "name": "nombre1",
        "last_name": "apellido1",
        "telephone": "987654321",
        "email": "test1@loadingplay.com",
        "deleted": true,
        "first_view": [FIRST_VIEW],
        "last_view": [LAST_VIEW]
    }
}
```

This endpoint delete a Customer.

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/customer/CUSTOMER_ID`

### URL Parameters

Parameter   | Default    | Description
----------- | ---------- | -----------
CUSTOMER_ID | (required) | identificador unico para customer




## Get a Customer list

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/customer \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d "site_name=test"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "customers": [
        {
            "id": [ID],
            "rut": "rut",
            "name": "nombre",
            "last_name": "apellido",
            "telephone": "123456789",
            "email": "test@loadingplay.com",
            "type": "persona",
            "deleted": false,
            "site_name": "test",
            "registration_date": [REGISTRATION_DATE],
            "first_view": [FIRST_VIEW],
            "last_view": [LAST_VIEW]
        },
        {
            "id": [ID],
            "rut": "rut2",
            "name": "nombre2",
            "last_name": "apellido2",
            "telephone": "987654321",
            "email": "test2@loadingplay.com",
            "type": "persona",
            "deleted": false,
            "site_name": "test",
            "registration_date": [REGISTRATION_DATE],
            "first_view": [FIRST_VIEW],
            "last_view": [LAST_VIEW]
        },
        ...
    ]
}
```

This endpoint retrieves a Customer list.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/customer`

### URL Parameters

Parameter | Default    | Description
--------- | ---------- | -----------
site_name | (required) | nombre de sitio del cual pertenece customer
