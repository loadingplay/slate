# Key Value Data

## Post Key Value


```shell
curl -XPOST 'https://apibodegas.loadingplay.com/v1/keyvaluedata' \
    -H 'Authorization: Bearer ACCESS_TOKEN' \
    -d 'key=key' \
    -d 'value=value'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "keyvaluedata": {
    "value": {
      "type": "[type]",
      "id": "[id]",
      "value": "[{value} or  'value']"
    },
    "key": "[key]"
  }
}
```

This endpoint retrieves info about Key Value Data added

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/keyvaluedata`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
key | (requerido) | key name for the value added
value | string | this field can be a string or a dictionary structure

<aside class="success">
Remember — ACCESS_TOKEN is mandatory for this action
</aside>

## Get a Specific Key Value Data

```shell
curl -XGET "https://apibodegas.loadingplay.com/v1/keyvaluedata/llave"
  -H 'Authorization: Bearer ACCESS_TOKEN' \
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "keyvaluedata": {
    "value": "[{value} or  'value']",
    "key": "[key]"
  }
}
```

This endpoint retrieves a specific kitten.

### HTTP Request

`GET https://apibodegas.loadingplay.com/v1/keyvaluedata/<key>`

### URL Parameters

Parameter | Description
--------- | -----------
key | The Key of the key value data requiered

<aside class="success">
Remember — ACCESS_TOKEN is mandatory for this action
</aside>

