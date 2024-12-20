---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - curl
  - javascript
  - php

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

Welcome to the StockFox API! You can use our API to access StockFox API endpoints, which can get information on various stocks, market trends, and financial data in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```curl
curl -X GET "https://primarysystems.aiml.monster/stockfox/api/v1/symbol/"
```

```javascript
fetch("https://primarysystems.aiml.monster/stockfox/api/v1/symbol/")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error));
```

```php
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://primarysystems.aiml.monster/stockfox/api/v1/symbol/");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);

if ($response === false) {
    echo "cURL Error: " . curl_error($ch);
}

curl_close($ch);

echo $response;
?>
```

> Make sure to replace `stockfoxapi` with your API key.

StockFox uses API keys to allow access to the API. You can register a new StockFox API key at our [developer portal](https://stockfox.ai/developers).

StockFox expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: stockfoxapi`

<aside class="notice">
You must replace <code>stockfoxapi</code> with your personal API key.
</aside>

# Symbol

## Get All Symbol

```curl
curl -X GET "https://primarysystems.aiml.monster/stockfox/api/v1/symbol/"
```

```javascript
fetch("https://primarysystems.aiml.monster/stockfox/api/v1/symbol/")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error));
```

```php
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://primarysystems.aiml.monster/stockfox/api/v1/symbol/");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);

if ($response === false) {
    echo "cURL Error: " . curl_error($ch);
}

curl_close($ch);

echo $response;
?>
```

> The above command returns JSON structured like this:

```json
[
  {
    "sid": "nasdaq:aapl",
    "symbol": "AAPL",
    "name": "Apple",
    "market": "NASDAQ",
    "icon": "https://logo.stocklight.com/NASDAQ/AAPL_icon.png",
    "summary": {
      "market": "NASDAQ",
      "symbol": "AAPL",
      "price": 249.79,
      "volume": 58911560,
      "marketCap": 3775775375360,
      "currency": "USD"
    }
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET https://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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

