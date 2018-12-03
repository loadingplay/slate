# Product tags

## Add a Tag to a product

this method will add a tag if doesn't exists, and do nothing if exists.

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/product/[SKU]/tags" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
    -d "tag=tag1,tag2"
```

> The above command returns json with tags info:

```json
{
  "status": "success",
  "tags": "tag1,tag2"
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/product/[SKU]/tags`

### Url Arguments

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| SKU       | (required) | unique identifier for product   |

### Query Parameters

| Parameter         | Description                      |
| ----------------- | -------------------------------- |
| tag (str)         | a list of tag separated by comma |




## Get tags from a product

this method will get all tag from a product.

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/product/[SKU]/tags" \
  -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json with tags info:

```json
{
  "status": "success",
  "tags": "tag1,tag2"
}
```

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/product/[SKU]/tags`

### Url Arguments

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| SKU       | (required) | unique identifier for product   |





## Remove a list of tag from a product

this method will remove a list of tag from a product.

```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/product/[SKU]/tags" \
  -H "Authorization: Bearer ACCESS_TOKEN" \
  -d "tag=tag1,tag2"
```

> The above command returns json with tags info:

```json
{
  "status": "success",
  "tags": ""
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/product/[SKU]/tags`

### Url Arguments

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| SKU       | (required) | unique identifier for product   |

### Query Parameters

| Parameter         | Description                                           |
| ----------------- | ----------------------------------------------------- |
| tag (str)         | a list of tag that will be removed separated by comma |
