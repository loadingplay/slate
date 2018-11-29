# Product tags

## Add a Tags to a product

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
