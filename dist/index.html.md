---
title: Products & Orders API v1.0.1
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="products-and-orders-api">Products & Orders API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:3000">http://localhost:3000</a>

* <a href="https://tyobce1cv8.execute-api.ap-southeast-2.amazonaws.com/latest">https://tyobce1cv8.execute-api.ap-southeast-2.amazonaws.com/latest</a>

# Authentication

* API Key (apiKeyAuth)
    - Parameter Name: **x-api-key**, in: header. 

<h1 id="products-and-orders-api-products">Products</h1>

## getProducts

<a id="opIdgetProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/products \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
GET http://localhost:3000/api/products HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/products',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'http://localhost:3000/api/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('http://localhost:3000/api/products', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/api/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/api/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/products`

*Returns a list of products from the database*

> Example responses

> 200 Response

```json
[
  {
    "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
    "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
    "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
    "model": "794297-0100",
    "sku": "394807",
    "cost": 445,
    "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
  }
]
```

<h3 id="getproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of current products|[ProductsList](#schemaproductslist)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## createProduct

<a id="opIdcreateProduct"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/products \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
POST http://localhost:3000/api/products HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/products',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'http://localhost:3000/api/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('http://localhost:3000/api/products', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:3000/api/products', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/products");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/api/products", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/products`

*Create a new product in the database*

> Body parameter

```json
{
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}
```

<h3 id="createproduct-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewProduct](#schemanewproduct)|true|Product information|

> Example responses

> 201 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}
```

<h3 id="createproduct-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Product was created successfully|[ViewProduct](#schemaviewproduct)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Location|string||The URL of the new product that was just created.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## getProductById

<a id="opIdgetProductById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/products/{productId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
GET http://localhost:3000/api/products/{productId} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/products/{productId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'http://localhost:3000/api/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('http://localhost:3000/api/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/api/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/products/{productId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/api/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/products/{productId}`

*Get a product from the database*

<h3 id="getproductbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|product Id to be retrieved|

> Example responses

> 200 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}
```

<h3 id="getproductbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Product retrieved successfully|[ViewProduct](#schemaviewproduct)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## updateProductById

<a id="opIdupdateProductById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/products/{productId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
PUT http://localhost:3000/api/products/{productId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/products/{productId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.put 'http://localhost:3000/api/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.put('http://localhost:3000/api/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:3000/api/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/products/{productId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/api/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/products/{productId}`

*Create a new product in the database*

> Body parameter

```json
{
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}
```

<h3 id="updateproductbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewProduct](#schemanewproduct)|true|Product information|
|productId|path|string|true|product Id to be retrieved|

> Example responses

> 200 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}
```

<h3 id="updateproductbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Product was created successfully|[ViewProduct](#schemaviewproduct)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Location|string||The URL of the new product that was just updated.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## deleteProduct

<a id="opIddeleteProduct"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/products/{productId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
DELETE http://localhost:3000/api/products/{productId} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/products/{productId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:3000/api/products/{productId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.delete('http://localhost:3000/api/products/{productId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:3000/api/products/{productId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/products/{productId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:3000/api/products/{productId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/products/{productId}`

*Delete a product from the database*

<h3 id="deleteproduct-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|productId|path|string|true|product Id to be retrieved|

> Example responses

> 400 Response

```json
{
  "status": "OK",
  "message": "The service did not work as expected."
}
```

<h3 id="deleteproduct-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Product deleted successfully|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

<h1 id="products-and-orders-api-orders">Orders</h1>

## getOrders

<a id="opIdgetOrders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/orders \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
GET http://localhost:3000/api/orders HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/orders',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'http://localhost:3000/api/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('http://localhost:3000/api/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/api/orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/api/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/orders`

*Returns a list of orders from the database*

> Example responses

> 200 Response

```json
[
  {
    "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
    "status": "OPEN",
    "date": "2022-03-12T23:20:50.52Z",
    "productIds": [
      "a1805cde-f34f-4945-9fec-3e096fef4bdd"
    ],
    "cost": 948.32,
    "tax": 94.83,
    "taxRate": 10,
    "total": 1043.152
  }
]
```

<h3 id="getorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of current orders|[OrdersList](#schemaorderslist)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## createOrder

<a id="opIdcreateOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/orders \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
POST http://localhost:3000/api/orders HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/orders',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'http://localhost:3000/api/orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('http://localhost:3000/api/orders', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:3000/api/orders', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/orders");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/api/orders", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/orders`

*Create a new order in the database*

> Body parameter

```json
{
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}
```

<h3 id="createorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewOrder](#schemaneworder)|true|Order information|

> Example responses

> 201 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}
```

<h3 id="createorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Order was created successfully|[ViewOrder](#schemavieworder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Location|string||The URL of the new order that was just created.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## getOrderById

<a id="opIdgetOrderById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/orders/{orderId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
GET http://localhost:3000/api/orders/{orderId} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/orders/{orderId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'http://localhost:3000/api/orders/{orderId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('http://localhost:3000/api/orders/{orderId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/api/orders/{orderId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/orders/{orderId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/api/orders/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /api/orders/{orderId}`

*Get an order from the database*

<h3 id="getorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|string|true|Order Id to be retrieved|

> Example responses

> 200 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}
```

<h3 id="getorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order retrieved successfully|[ViewOrder](#schemavieworder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## updateOrderById

<a id="opIdupdateOrderById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/orders/{orderId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
PUT http://localhost:3000/api/orders/{orderId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/orders/{orderId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.put 'http://localhost:3000/api/orders/{orderId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.put('http://localhost:3000/api/orders/{orderId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:3000/api/orders/{orderId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/orders/{orderId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/api/orders/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /api/orders/{orderId}`

*Create a new order in the database*

> Body parameter

```json
{
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}
```

<h3 id="updateorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NewOrder](#schemaneworder)|true|Order information|
|orderId|path|string|true|Order Id to be retrieved|

> Example responses

> 200 Response

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}
```

<h3 id="updateorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order was updated successfully|[ViewOrder](#schemavieworder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Location|string||The URL of the new order that was just updated.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

## deleteOrder

<a id="opIddeleteOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/orders/{orderId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```http
DELETE http://localhost:3000/api/orders/{orderId} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('http://localhost:3000/api/orders/{orderId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.delete 'http://localhost:3000/api/orders/{orderId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.delete('http://localhost:3000/api/orders/{orderId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:3000/api/orders/{orderId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/api/orders/{orderId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-api-key": []string{"API_KEY"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:3000/api/orders/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /api/orders/{orderId}`

*Delete an order from the database*

<h3 id="deleteorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|string|true|Order Id to be retrieved|

> Example responses

> 400 Response

```json
{
  "status": "OK",
  "message": "The service did not work as expected."
}
```

<h3 id="deleteorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Order deleted successfully|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyAuth
</aside>

# Schemas

<h2 id="tocS_ProductsList">ProductsList</h2>
<!-- backwards compatibility -->
<a id="schemaproductslist"></a>
<a id="schema_ProductsList"></a>
<a id="tocSproductslist"></a>
<a id="tocsproductslist"></a>

```json
[
  {
    "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
    "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
    "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
    "model": "794297-0100",
    "sku": "394807",
    "cost": 445,
    "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ViewProduct](#schemaviewproduct)]|false|none|none|

<h2 id="tocS_ViewProduct">ViewProduct</h2>
<!-- backwards compatibility -->
<a id="schemaviewproduct"></a>
<a id="schema_ViewProduct"></a>
<a id="tocSviewproduct"></a>
<a id="tocsviewproduct"></a>

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(guid)|true|none|The ID of the Product|
|name|string|true|none|The name of the Product|
|description|string|true|none|The description of the Product|
|model|string|true|none|The model number of the Product|
|sku|string|true|none|The SKU of the Product|
|cost|number(float)|true|none|The cost of the Product|
|imageUrl|string(url)|true|none|The URL to the image of the Product|

<h2 id="tocS_NewProduct">NewProduct</h2>
<!-- backwards compatibility -->
<a id="schemanewproduct"></a>
<a id="schema_NewProduct"></a>
<a id="tocSnewproduct"></a>
<a id="tocsnewproduct"></a>

```json
{
  "name": "Bose Noise Cancelling Over-Ear Headphones 700 (Black)",
  "description": "- 11 levels of noise cancelling\n- Google Assistant and Amazon Alexa built in\n- 20 hours of battery life\n",
  "model": "794297-0100",
  "sku": "394807",
  "cost": 445,
  "imageUrl": "https://cdn.shopify.com/s/files/1/0024/9803/5810/products/394807-Product-0-I_d1664990-4dfb-462f-bb93-2fb469ed7d5d_800x800.jpg"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|The name of the Product|
|description|string|true|none|The description of the Product|
|model|string|true|none|The model number of the Product|
|sku|string|true|none|The SKU of the Product|
|cost|number(float)|true|none|The cost of the Product|
|imageUrl|string(url)|true|none|The image URL of the Product|

<h2 id="tocS_OrdersList">OrdersList</h2>
<!-- backwards compatibility -->
<a id="schemaorderslist"></a>
<a id="schema_OrdersList"></a>
<a id="tocSorderslist"></a>
<a id="tocsorderslist"></a>

```json
[
  {
    "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
    "status": "OPEN",
    "date": "2022-03-12T23:20:50.52Z",
    "productIds": [
      "a1805cde-f34f-4945-9fec-3e096fef4bdd"
    ],
    "cost": 948.32,
    "tax": 94.83,
    "taxRate": 10,
    "total": 1043.152
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ViewOrder](#schemavieworder)]|false|none|none|

<h2 id="tocS_ViewOrder">ViewOrder</h2>
<!-- backwards compatibility -->
<a id="schemavieworder"></a>
<a id="schema_ViewOrder"></a>
<a id="tocSvieworder"></a>
<a id="tocsvieworder"></a>

```json
{
  "id": "a1805cde-f34f-4945-9fec-3e096fef4bdd",
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(guid)|true|none|The ID of the Order|
|status|string|true|none|The status of the Order|
|date|string(date-time)|true|none|The date of the Order|
|productIds|[string]|true|none|none|
|cost|number(float)|true|none|The cost of the Order less tax|
|tax|number(float)|true|none|The sales tax of the Order|
|taxRate|number(float)|true|none|The rate at which the sales tax is calculated on the Order|
|total|number(float)|true|none|The cost plus the sales tax of the Order|

#### Enumerated Values

|Property|Value|
|---|---|
|status|OPEN|
|status|PAID|
|status|SHIPPED|
|status|RECEIVED|

<h2 id="tocS_NewOrder">NewOrder</h2>
<!-- backwards compatibility -->
<a id="schemaneworder"></a>
<a id="schema_NewOrder"></a>
<a id="tocSneworder"></a>
<a id="tocsneworder"></a>

```json
{
  "status": "OPEN",
  "date": "2022-03-12T23:20:50.52Z",
  "productIds": [
    "a1805cde-f34f-4945-9fec-3e096fef4bdd"
  ],
  "cost": 948.32,
  "tax": 94.83,
  "taxRate": 10,
  "total": 1043.152
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|true|none|The status of the Order|
|date|string(date-time)|true|none|The date of the Order|
|productIds|[string]|true|none|none|
|cost|number(float)|true|none|The cost of the Order|
|tax|number(float)|true|none|The sales tax of the Order|
|taxRate|number(float)|true|none|The percentage at which the sales tax is calculated.|
|total|number(float)|true|none|The cost plus the sales tax of the Order|

#### Enumerated Values

|Property|Value|
|---|---|
|status|OPEN|
|status|PAID|
|status|SHIPPED|
|status|RECEIVED|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "status": "OK",
  "message": "The service did not work as expected."
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|true|none|The status code of the error|
|message|string|false|none|The message detailing what happened.|

