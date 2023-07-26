---
title: Play Oxygen v1.0
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

<h1 id="play-oxygen">Play Oxygen v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:4000">http://localhost:4000</a>

<h1 id="play-oxygen-clients">clients</h1>

## Po2Web.ClientController.create

<a id="opIdPo2Web.ClientController.create"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:4000/api/int/clients/create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:4000/api/int/clients/create HTTP/1.1
Host: localhost:4000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "id": "client_1234567890",
  "name": "Big Company",
  "prefix": "big_company"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:4000/api/int/clients/create',
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
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:4000/api/int/clients/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:4000/api/int/clients/create', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:4000/api/int/clients/create', array(
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
URL obj = new URL("http://localhost:4000/api/int/clients/create");
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
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:4000/api/int/clients/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /api/int/clients/create`

*Create client*

> Body parameter

```json
{
  "id": "client_1234567890",
  "name": "Big Company",
  "prefix": "big_company"
}
```

<h3 id="po2web.clientcontroller.create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|path|string|true|Client name|
|body|body|[Client](#schemaclient)|false|Client params|

> Example responses

> 200 Response

```json
{
  "id": "client_1234567890",
  "name": "Big Company",
  "prefix": "big_company"
}
```

<h3 id="po2web.clientcontroller.create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Client response|[Client Response](#schemaclient response)|

### Callbacks

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None ( Scopes: create:client )
</aside>

# Schemas

<h2 id="tocS_Client">Client</h2>
<!-- backwards compatibility -->
<a id="schemaclient"></a>
<a id="schema_Client"></a>
<a id="tocSclient"></a>
<a id="tocsclient"></a>

```json
{
  "id": "client_1234567890",
  "name": "Big Company",
  "prefix": "big_company"
}

```

Client

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|uuid|false|none|Client ID|
|name|string|true|none|Client name|
|prefix|string|false|none|Schema prefix for data storage|

<h2 id="tocS_Client Response">Client Response</h2>
<!-- backwards compatibility -->
<a id="schemaclient response"></a>
<a id="schema_Client Response"></a>
<a id="tocSclient response"></a>
<a id="tocsclient response"></a>

```json
{
  "id": "client_1234567890",
  "name": "Big Company",
  "prefix": "big_company"
}

```

Client Response

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[Client](#schemaclient)|false|none|A Play Oxygen customer|

