# Cellars

## Create a cellar

```shell
curl -XPOST "https://apibodegas.loadingplay.com/v1/cellar" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "name=name" \
     -d "site_name=test"
```

> The above command returns json with cellar info, including id:

```json
{
    "status": "success",
    "cellar": {
        "id": "[cellar_id]",
        "name": "[cellar_name]",
        "site_name": "[site_name]"
    }
}
```

### HTTP Request

`POST https://apibodegas.loadingplay.com/v1/cellar`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
name         | (required) | name of the cellar
site_name    | (required) | name of the site where cellar will be created




## Delete a cellar

```shell
curl -XDELETE "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN"
```

> The above command returns json:

```json
{
    "status": "success",
    "cellar": "[cellar_id]"
}
```

### HTTP Request

`DELETE https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
cellar_id | (required) | unique identifier for cellar

## Edit a cellar

```shell
curl -XPUT "https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]" \
     -H "Authorization: Bearer ACCESS_TOKEN" \
     -d "name=[new_name]" \
     -d "description=[new_description]" \
     -d "for_sale=[true|false]" \
     -d "reservation=[true|false]"
```

> The above command returns json:

```json
{
    "status": "success",
    "cellar": {
        "id": "[id]",
        "name": "[name]",
        "description": "[description]",
        "for_sale": "[for_sale]",
        "reservation": "[reservation]"
    }
}
```

### HTTP Request

`PUT https://apibodegas.loadingplay.com/v1/cellar/[cellar_id]`

### URL Parameters

Parameter    | Default    | Description
------------ | ---------- | -----------
cellar_id | (required) | unique identifier for cellar
name | (optional) | name of the cellar
description | (optional) | description of the cellar
for_sale | (optional) | true if this cellar is enabled for web, the system will allow only one cellar as web
reservation | (optional) | true if this cellar is enabled for reservation, the system will allow only one cellar as reservation
