# Product images

## Add images to a product

to generate image and thumbnails see https://static.loadingplay.com

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/product/[SKU]/images \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d "site_name=fm" \
    -d "url=original image url" \
    -d "thumb_1=smallest possible thumbnail url" \
    -d "thumb_200=200px thumbnail url" \
    -d "thumb_500=500px thumbnail url"
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "images": [{
    "url": "original image url",
    "thumb_1": "smallest possible thumbnail url",
    "thumb_200": "200px thumbnail url",
    "thumb_500": "500px thumbnail url"
  }]
}
```

This endpoint retrieves a list of images.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/product/[SKU]/images`

### Query Parameters

| Parameter | Default    | Description                     |
| --------- | ---------- | ------------------------------- |
| site_name | (required) | filter by site                  |
| url       | (required) | original picture thumbnail url  |
| thumb_1   | (required) | smallest possible thumbnail url |
| thumb_200 | (required) | 200px thumbnail url             |
| thumb_500 | (required) | 500px thumbnail url             |
