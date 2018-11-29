# Products

## Create a Product

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/product" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "sku=2212110" \
    -d "name=" \
    -d "description=" \
    -d "main_price=" \
    -d "cost_price=" \
    -d "promotion_price=" \
    -d "bulk_price=" \
    -d "brand=" \
    -d "manufacturer=" \
    -d "bullet_1=" \
    -d "bullet_2=" \
    -d "bullet_3="
```

> The above command returns json with product info, including id:

```json
{
  "status": "success",
  "product": {
    "id": [product_id],
    "sku": [product_sku]
  }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/product`

### URL Parameters

| Parameter | Description                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------- |
| sku       | (required) unique identifier for product it can be a comma separated list, and return a comma separated list of products |

## Edit a Product

```shell
curl -XPUT "https://apibodegas.loadingplay.com/v1/product" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "sku=2212110" \
    -d "name=" \
    -d "description=" \
    -d "main_price=" \
    -d "cost_price=" \
    -d "promotion_price=" \
    -d "bulk_price=" \
    -d "brand=" \
    -d "manufacturer=" \
    -d "bullet_1=" \
    -d "bullet_2=" \
    -d "bullet_3="
```

> The above command returns json with product info, including id:

```json
{  
   "status":"success",
   "product":{  
      "bullet_1": [bullet_1],
      "description": [description],
      "bullet_3": [bullet_3],
      "bullet_2": [bullet_2],
      "brand": [brand],
      "id": [id],
      "manufacturer": [manufacturer],
      "sku": [sku],
      "name": [name],
      "for_sale": [for_sale],
      "main_price": [main_price],
      "position": [position],
      "promotion_price": [promotion_price],
      "cost_price": [cost_price]
   }
}
```

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/product`

### URL Parameters

| Parameter | Description                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------- |
| sku       | (required) unique identifier for product it can be a comma separated list, and return a comma separated list of products |

## Get a single Product

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/product" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -d "site_name=fm" \
  -d "sku=2212110"
```

> The above command returns JSON structured like this:

```json
{  
   "status": "success",
   "product": [  
        {
            "brand": "Cat Chow",
            "bulk_price": 0.0,
            "bullet_1": "Alimento Para Gato Adulto Sabor Pescado",
            "bullet_2": "15 Kilos",
            "bullet_3": "",
            "cost_price": 30484.0,
            "critical_stock": 1,
            "description": "PURINA CAT CHOW Adultos te ofrece un alimento 100% completo y balanceado desarrollado especialmente para los gatos de 1-7 a\u00f1os de edad que le podr\u00e1 ayudar a mantener un desarrollo sano de su coraz\u00f3n y un sistema inmunol\u00f3gico m\u00e1s fuerte gracias a su contenido de: Grasas, Minerales, Vitaminas y Antioxidantes.<br/><br/>Formato de Venta: Bolsa<br/><br/> Delivery: Entre 24 y 72 horas<br/><br/>*Foto de producto referencial<br/>",
            "enabled": false,
            "for_sale": true,
            "id": 1237,
            "images": [  
                {  
                   "url": "https://7static.loadingplay.com/static/images/4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                   "thumb_500": "https://7static.loadingplay.com/static/images/500_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                   "thumb_1": "https://84static.loadingplay.com/static/images/1_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                   "id": 29,
                   "thumb_200": "https://7static.loadingplay.com/static/images/200_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png"
                }
            ],
            "main_price": 39903.0,
            "manufacturer": "Purina",
            "name": "Cat Chow Adulto | Alimento Para Gato Adulto Sabor Pescado",
            "position": 0,
            "profit_margin": 9419.0,
            "promotion_price": 0.0,
            "site_name": "fm",
            "sku": "2212110",
            "tags": "15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,15_kilos,cat_chow,cat_chow,cat_chow,cat_chow,cat_chow",
            "upp": 1,
            "weight": 0.0,
            "in_stock": true
      }
   ]
}
```

This endpoint retrieves a specific product.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/product`

### URL Parameters

| Parameter | Description                                                                                                   |
| --------- | ------------------------------------------------------------------------------------------------------------- |
| site_name | (required) filter by site                                                                                     |
| sku       | unique identifier for product it can be a comma separated list, and return a comma separated list of products |


## Get all Products

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/product/list \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d "site_name=fm"
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "metadata": { "total_records": 169, "records_filtered": 100 },  // only if enabled
    "products": [
        {
            "balance_units": 44,
            "brand": "CAT CHOW",
            "bulk_price": 1,
            "bullet_1": "Alimento para gato adulto, Pescado y Mariscos",
            "bullet_2": "15k",
            "bullet_3": "",
            "cost_price": 29277,
            "critical_stock": 1,
            "description": "product description",
            "enabled": false,
            "for_sale": true,
            "id": 1237,
            "images": [
                "https://7static.loadingplay.com/static/images/4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                "https://84static.loadingplay.com/static/images/1_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                "https://7static.loadingplay.com/static/images/200_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png",
                "https://7static.loadingplay.com/static/images/500_4799bd4dd9fdc1599355e6743ed9580c_PESCADO2.png.png"
            ],
            "main_price": 29277,
            "manufacturer": "Nestle",
            "name": "Cat Chow Adultos",
            "position": 0,
            "profit_margin": 0,
            "promotion_price": 0,
            "site_id": 2,
            "sku": "2212110",
            "tags": "gato",
            "upp": 1,
            "weight": 0
        },
        ....
    ]
}
```

This endpoint retrieves a Products list.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/product/list`

### Query Parameters

| Parameter | Default      | Description                           |
| --------- | ------------ | ------------------------------------- |
| site_name | (required)   | filter by site                        |
| page      | 1            | startig page                          |
| items     | 10           | items to show per page                |
| metadata  | false        | true if you need to return total rows |
| search    | ''           | perform a search in products          |
| column    | 'main_price' | column for sorting items              |
| order     | 'ASC'        | type of orden DESC or ASC             |


## Create a Tag in a product

this method will add a tag if doesn't exists, and do nothing if exists.

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/product/[SKU]/tags" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "tag=new_tag"
```

> The above command returns json with tags info, including id:

```json
{
  "status": "success",
  "tags": [
    {
        "id": [tag_id],
        "name": [tag_name]
    },
    ...
  ]
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/product/[SKU]/tags`

### URL Parameters

| Parameter         | Description               |
| ----------------- | ------------------------- |
| product_sku (str) | product unique identifier |
| tag (str)         | tag that will be added    |
