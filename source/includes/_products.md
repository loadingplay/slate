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
    -d "metadata=true"
```

> The above command returns JSON structured like this:

```json
{  
   "status":"success",
   "metadata":{  
      "total_records":5,
      "records_filtered":5
   }
   "products":[  
        {  
            "bulk_price":0.0,
            "site_name":"test4",
            "weight":0.0,
            "bullet_2":"",
            "images":[  
                {  
                   "sort":0,
                   "thumb_500":"https://84static.loadingplay.com/static/images/500_a679babb48aebafabb636d7d3e1e8485_Complementa_jpg.png",
                   "name":"",
                   "url":"https://84static.loadingplay.com/static/images/a679babb48aebafabb636d7d3e1e8485_Complementa_jpg.png",
                   "image":"",
                   "thumb_1":"https://84static.loadingplay.com/static/images/1_a679babb48aebafabb636d7d3e1e8485_Complementa_jpg.png",
                   "thumb_200":"https://84static.loadingplay.com/static/images/200_a679babb48aebafabb636d7d3e1e8485_Complementa_jpg.png",
                   "id":46247,
                   "product_id":5394
                },
                {  
                   "sort":1,
                   "thumb_500":"https://7static.loadingplay.com/static/images/500_14b9c0991214015b96cca1c6769bb3d5_Complementa_40.jpg.png",
                   "name":"",
                   "url":"https://7static.loadingplay.com/static/images/14b9c0991214015b96cca1c6769bb3d5_Complementa_40.jpg.png",
                   "image":"",
                   "thumb_1":"https://7static.loadingplay.com/static/images/1_14b9c0991214015b96cca1c6769bb3d5_Complementa_40.jpg.png",
                   "thumb_200":"https://7static.loadingplay.com/static/images/200_14b9c0991214015b96cca1c6769bb3d5_Complementa_40.jpg.png",
                   "id":46248,
                   "product_id":5394
                },
                {  
                   "sort":2,
                   "thumb_500":"https://7static.loadingplay.com/static/images/500_f1d8fc53401ea65ab59046d4d482cbc5_Complementa_41.jpg.png",
                   "name":"",
                   "url":"https://7static.loadingplay.com/static/images/f1d8fc53401ea65ab59046d4d482cbc5_Complementa_41.jpg.png",
                   "image":"",
                   "thumb_1":"https://7static.loadingplay.com/static/images/1_f1d8fc53401ea65ab59046d4d482cbc5_Complementa_41.jpg.png",
                   "thumb_200":"https://7static.loadingplay.com/static/images/200_f1d8fc53401ea65ab59046d4d482cbc5_Complementa_41.jpg.png",
                   "id":46249,
                   "product_id":5394
                },
                {  
                   "sort":3,
                   "thumb_500":"https://84static.loadingplay.com/static/images/500_141da80a3ad557b1d5d9bb590f7c5d0a_Complementa_jpg.png",
                   "name":"",
                   "url":"https://84static.loadingplay.com/static/images/141da80a3ad557b1d5d9bb590f7c5d0a_Complementa_jpg.png",
                   "image":"",
                   "thumb_1":"https://84static.loadingplay.com/static/images/1_141da80a3ad557b1d5d9bb590f7c5d0a_Complementa_jpg.png",
                   "thumb_200":"https://84static.loadingplay.com/static/images/200_141da80a3ad557b1d5d9bb590f7c5d0a_Complementa_jpg.png",
                   "id":46250,
                   "product_id":5394
                }
            ],
            "bullet_1":"Coj\u00edn ideal para la sala de estar de tu casa, donde puedes sentarte a leer un libro y compartir con tu familia",
            "id":5394,
            "sku":"CO-1113",
            "bullet_3":"",
            "profit_margin":35000.0,
            "main_price":35000.0,
            "cost_price":0.0,
            "description":"Este es un coj\u00edn ideal para las tardes de la semana donde tus hijos compartiran en la sala de estar mientras hacen las tareas, comparten com amigos o simplemente disfrutan en familia.",
            "tags":"terraza,terraza",
            "brand":"Complementa",
            "in_stock":true,
            "manufacturer":"Complementa",
            "name":"Cojin Sala de estar",
            "enabled":false,
            "for_sale":true,
            "promotion_price":0.0,
            "position":0,
            "critical_stock":1,
            "upp":1
        },
        ...
    ]
}
```

This endpoint retrieves all Products from a site.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/product/list`

### Query Parameters

| Parameter     | Default | Description                           |
| ------------- | ------- | ------------------------------------- |
| page          | 0       | startig page                          |
| items         | 10      | items to show per page                |
| column        | 'name'  | column for sorting items              |
| order         | 'asc'   | type of orden DESC or ASC             |
| search        | ''      | perform a search in products          |
| tags          | ''      | tags to search for                    |
| for_sale_only | 'false' | true if you want return only for sale |
| metadata      | False   | true if you need to return total rows |
