# Orders

## Create Order

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/order \
    -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "rut=1111111-1" \
    -d "name=Sebastian" \
    -d "last_name=Benavente" \
    -d "telephone=55555555" \
    -d "email=seba@mail.com" \
    -d "address=direccion testtest" \
    -d "additional_info=informacion relevante al despacho" \
    -d "city=" \
    -d "region=III Región Atacama" \
    -d "town=Copiapó" \
    -d "zip_code=" \
    -d "shipping=0" \
    -d "extra_info=" \
    -d "origin=web" \
    -d "payment_type=Webpay" \
    -d "voucher=" \
    -d "reference_code=" \
    -d "cellar_id=" \
    -d "tax=0" \
    -d "products=[{'sku': 'sku1', 'price': 33558, 'name': 'producto 1', 'combination': 's', 'quantity': 1}]"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "order":{  
        "origin":"web",
        "provider_id":null,
        "site_name":"baymax",
        "tax":0.0,
        "tracking_code":"",
        "voucher":"",
        "adjustment":0.0,
        "id":14485,
        "extra_info":"",
        "items_quantity":null,
        "total":33558.0,
        "shipping_id":12583,
        "url_document":null,
        "source":"",
        "state":1,
        "customer_id":2150,
        "type":1,
        "discount_code":"",
        "status":"por confirmar",
        "deleted":false,
        "site_id":null,
        "products_quantity":null,
        "date":"2018-12-04T16:04:59.111407",
        "subtotal":33558.0,
        "name":"",
        "cellar_id":111,
        "shipping":0,
        "payment_type":"Webpay",
        "reference_code":"",
        "billing_id":12583
    }
}
```

This endpoint add an Order.

### HTTP Request

`POST https://apibodegas.loadingplay.com/order`

### Query Parameters

| Parameter       | Default | Description                                  |
| --------------- | ------- | -------------------------------------------- |
| rut             | str     | buyer rut                                    |
| name            | str     | buyer name                                   |
| last_name       | str     | buyer lastname                               |
| telephone       | str     | buyer telephone                              |
| email           | str     | buyer email                                  |
| address         | str     | buyer address                                |
| additional_info | str     | buyer additional info in realtion to address |
| city            | str     | buyer city                                   |
| region          | str     | buyer region                                 |
| town            | str     | buyer town                                   |
| zip_code        | str     | buyer zip_code                               |
| shipping        | int     | shipping price                               |
| extra_info      | str     | order extra_info                             |
| origin          | str     | order origin                                 |
| payment_type    | str     | payment type                                 |
| voucher         | str     | orders voucher                               |
| reference_code  | str     | orders reference_code                        |
| cellar_id       | str     | orders cellar_id                             |
| tax             | int     | orders tax                                   |
| products        | str     | products in relation to order_detail         |




## List Orders

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/order
    -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "page=1" \
    -d "items=10"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "orders": [
        {
        "origin": "site_name",
        "provider_id": null,
        "site_name": "site_name",
        "site_id": null,
        "tracking_code": "35345",
        "voucher": "https://84static.loadingplay.com/static/images/500_ca68f77b6d1381225e5aa3310158576c_Captura_de_pantalla__a_las__ampng.png",
        "total": 18490.0,
        "id": 4097,
        "extra_info": "",
        "items_quantity": null,
        "adjustment": 0.0,
        "user_id": 2738,
        "shipping_id": 2152,
        "url_document": null,
        "source": "",
        "state": 4,
        "type": 1,
        "transaction_id": null,
        "status": "4",
        "deleted": false,
        "tax": 0.0,
        "products_quantity": null,
        "discount": 0,
        "date": "2017-10-10T22:24:24.219831",
        "subtotal": 18490.0,
        "discount_code": "",
        "name": "",
        "shipping": 0,
        "payment_type": 10,
        "reference_code": "",
        "billing_id": 2152
        },
        ...
    ]
}
```

This endpoint retrieves a list of Orders.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/order`

### URL Parameters

| Parameter      | Default | Description                                     |
| -------------- | ------- | ----------------------------------------------- |
| page           | int     | page number. Defaults to 1                      |
| items          | int     | items per page. Defaults to 10                  |
| column         | str     | column for sorting. Defaults to id              |
| order          | str     | ASC or DESC sorting direction. Defaults to DESC |
| metadata       | bool    | true to show meta data of the query             |
| origin         | str     | filter orders by origin                         |
| reference_code | str     | filter orders by reference code                 |

## Get Order

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/order/[order_id]
    -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "order": {
    "origin": "site_name",
    "provider_id": null,
    "site_name": "site_name",
    "site_id": null,
    "tracking_code": "35345",
    "voucher": "https://84static.loadingplay.com/static/images/500_ca68f77b6d1381225e5aa3310158576c_Captura_de_pantalla__a_las__ampng.png",
    "total": 18490.0,
    "id": 4097,
    "extra_info": "",
    "items_quantity": null,
    "adjustment": 0.0,
    "user_id": 2738,
    "shipping_id": 2152,
    "url_document": null,
    "source": "",
    "state": 4,
    "type": 1,
    "transaction_id": null,
    "status": "4",
    "deleted": false,
    "tax": 0.0,
    "products_quantity": null,
    "discount": 0,
    "date": "2017-10-10T22:24:24.219831",
    "subtotal": 18490.0,
    "discount_code": "",
    "name": "",
    "shipping": 0,
    "payment_type": 10,
    "reference_code": "",
    "billing_id": 2152
  }
}
```

This endpoint retrieves an Order.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/order/[id]`

### URL Parameters

| Parameter | Default        | Description                 |
| --------- | -------------- | --------------------------- |
| id        | str (required) | unique identifier for order |

## Edit Order

```shell
curl -XPUT https://apibodegas.loadingplay.com/order \
    -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "id=4029" \
    -d "adjustment=" \
    -d "is_deleted=" \
    -d "discount_code=" \
    -d "extra_info=" \
    -d "origin=" \\
    -d "reference_code=" \
    -d "source=" \
    -d "status=" \
    -d "tracking_code=" \
    -d "voucher=" \
    -d "payment_type=" \
    -d "url_document=" \
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "order": {
    "origin": "Sitio Antiguo",
    "provider_id": null,
    "site_name": "site_name",
    "transaction_id": null,
    "site_id": null,
    "tracking_code": "codigodespacho",
    "voucher": "",
    "total": 0.0,
    "id": 4029,
    "extra_info": "",
    "items_quantity": null,
    "adjustment": 0.0,
    "user_id": 323,
    "shipping_id": 2084,
    "url_document": null,
    "source": "web",
    "state": 4,
    "type": 1,
    "discount_code": "",
    "status": "4",
    "deleted": false,
    "tax": 0.0,
    "products_quantity": null,
    "date": "2017-10-30T17:51:17.603750",
    "subtotal": 0.0,
    "name": "",
    "shipping": 0,
    "payment_type": 1,
    "reference_code": "",
    "billing_id": 2084
  }
}
```

This endpoint retrieves an Order.

### HTTP Request

`PUT https://apibodegas.loadingplay.com/order`

### URL Parameters

| Parameter      | Default        | Description                   |
| -------------- | -------------- | ----------------------------- |
| id             | str (required) | unique identifier for order   |
| adjustment     | str            | order adjustment              |
| is_deleted     | str            | dverify is a deleted order    |
| discount_code  | str            | discont code over the order   |
| extra_info     | str            | extra info into the order     |
| origin         | str            | origin from the order         |
| reference_code | str            | reference code into the order |
| source         | str            | source from the order         |
| status         | str            | order status                  |
| tracking_code  | str            | tracking code og the order    |
| voucher        | str            | orde voucher                  |
| payment_type   | str            | order payment type            |
| url_document   | str            | url document into the order   |

## Get products from Order

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/order/[id]/detail \
    -H "Authorization: Bearer ACCESS_TOKEN" \
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "products": [
    {
      "sku": "HA-E990-S18-WHI-SAN-CAS-T25",
      "product_id": null,
      "combination": "36",
      "order_id": 4097,
      "price": 18490,
      "name": "Sandalia Blanco / Beige Balasi",
      "order_name": "",
      "state": 4,
      "quantity": 1,
      "subtotal": 18490.0,
      "id": 5385,
      "size": ""
    }
  ]
}
```

This endpoint retrieves an Order Detail.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/order/[id]/detail`

### URL Parameters

| Parameter | Default        | Description                 |
| --------- | -------------- | --------------------------- |
| id        | str (required) | unique identifier for order |
