# Tags

## Create a Tag

```shell
curl -XPOST https://apibodegas.loadingplay.com/v1/tag \
    -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
    -d 'site_name=[site_name]' \
    -d 'name=[tag_name]'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "tag": {
    "name": "[tag_name]",
    "site_name": "[site_name]",
    "id": "[tag_id]"
  }
}
```

This endpoint creates a Tag on a site and return it's info

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/tag`

### Query Parameters

Parameter | Default | Data Type	| Description
--------- | ------- | ---------	| -----------
site_name | (required) | string | Site name 
name | (required)| string | Name of the tag

## Get the Data of a Tag

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/tag \
    -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
    -d 'site_name=[site_name]' \
    -d 'name=[tag_name]'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "tag": {
    "name": "[tag_name]",
    "site_name": "[site_name]",
    "id": "[tag_id]"
  }
}
```

This endpoint retrieves info about a previously created Tag

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/tag`

### Query Parameters

Parameter | Default | Data Type | Description
--------- | ------- | ---- |-----------
site_name | (required) | string |Site name 
name | (required) |string | Name of the tag

## Get Tag List of a Site

```shell
curl -XGET https://apibodegas.loadingplay.com/v1/tag/list \
    -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
    -d 'site_name=[site_name]' \
    -d 'page=[page]' \
    -d 'tags_per_page=[tags_per_page]'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "tags": [
  			{
		  		"visible": "visible", 
		  		"site_id": "site_id", 
		  		"id": "tag_id", 
		  		"name": "tag_name"
  			},
  			... # To the nth tag
  		  ]
}
```

This endpoint retrieves info about the tags of a site

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/tag`

### Query Parameters

Parameter | Default | Data Type | Description
--------- | ------- | ---- |-----------
site_name | (required) | string |Site name 
page 	  | (optional) | int    | List pagination number
tags_per_page | (optional) | int | Tags per page
