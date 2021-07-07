---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://www.ypso-facto.com'>Documentation Powered by Ypso-Facto</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Proxima Server API ! The API is used to access Proxima Server endpoints, which can retrieve various informations on users, collections, teams, locks... in our database.

We have language bindings in Shell, VB# and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "http://localhost:50376/api/v1" \
  -H "Authorization: Bearer private_access_token_key"
```

```javascript
// TODO
```

```vb
' TODO
```

> Make sure to replace `private_access_token_key` with your API key.

Proxima Server uses API keys to allow access to the API. API keys are obtained after a successfull authentication with an Ypso-Facto desktop or web application.

Proxima Server expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer private_access_token_key`

<aside class="notice">
You must replace <code>private_access_token_key</code> with your personal API key.
</aside>

# Users

## Get All Users

```shell
# With shell, you can just pass the correct header with each request
curl "http://192.168.1.20:5376/api/v1/users/all" \
  -H "Authorization: Bearer private_access_token_key"
```

```javascript
// TODO
```

```vb
' TODO
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET http://192.168.1.20:5376/api/v1/users/all`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
p1 | false | If set to true, the result will also include cats.
p2 | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember 
</aside>

## Get a Specific User

```shell
curl "http://192.168.1.20:5376/api/v1/users/view/id" \
  -H "Authorization: Bearer private_access_token_key"
```

```javascript
// TODO
```

```vb
' TODO
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

