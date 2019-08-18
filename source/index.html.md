---
title: Appointments management API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers:
  - '<a href="https://docs.google.com/spreadsheets">API design</a>'
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="appointments-management-api">Appointments management API v0.0.2-oas3</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Specification for appointment management service with notifications

Base URLs:

* <a href="http://localhost:3000/v1/">http://localhost:3000/v1/</a>

* <a href="https://localhost:3000/v1/">https://localhost:3000/v1/</a>

Email: <a href="mailto:david@dmbarreiro.com">David Martinez Barreiro</a> Web: <a href="https://www.dmbarreiro.com">David Martinez Barreiro</a> 
 License: All Rights Reserved

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **api_key**, in: header. 

- HTTP Authentication, scheme: basic 

- HTTP Authentication, scheme: bearer 

<h1 id="appointments-management-api-companies">companies</h1>

Companies using appointments service

## get__companies_{id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/companies/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/companies/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/companies/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/companies/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/companies/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/companies/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/companies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}`

*Returns single company information*

Returns company information identified by {id}

<h3 id="get__companies_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}
```

<h3 id="get__companies_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific company|[Company](#schemacompany)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Company not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__companies_{id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/v1/companies/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:3000/v1/companies/{id} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/companies/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/companies/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:3000/v1/companies/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:3000/v1/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/companies/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/v1/companies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /companies/{id}`

*Updates company information*

Updates company information data identified by {id} returning no information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}
```

<h3 id="put__companies_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Company](#schemacompany)|true|Contains company information to be updated on the record, must contain all company requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="put__companies_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Company not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__companies

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/companies \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/companies HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/companies',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/companies',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/companies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/companies");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/companies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies`

*Returns information from all companies*

Returns an array with information from each company

<h3 id="get__companies-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "notification_advance": 0,
    "created_at": "2019-08-17T22:45:37Z",
    "employees_id": [
      "string"
    ],
    "address": {
      "street": "string",
      "city": "string",
      "county": "string",
      "state": "string",
      "country": "string",
      "post_code": 0
    }
  }
]
```

<h3 id="get__companies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="get__companies-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Company](#schemacompany)]|false|none|none|
|» id|string|true|none|none|
|» name|string|true|none|none|
|» notification_advance|integer(int64)|false|none|none|
|» created_at|string(date-time)|true|none|none|
|» employees_id|[string]|false|none|none|
|» address|[Company_address](#schemacompany_address)|true|none|none|
|»» street|string|true|none|none|
|»» city|string|true|none|none|
|»» county|string|false|none|none|
|»» state|string|false|none|none|
|»» country|string|true|none|none|
|»» post_code|integer|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__companies

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/v1/companies \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:3000/v1/companies HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/companies',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/companies',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:3000/v1/companies',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:3000/v1/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/companies");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/v1/companies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /companies`

*Creates new company*

Creates new company returning no information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}
```

<h3 id="post__companies-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Company](#schemacompany)|true|Contains company information to be added to the record|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}
```

<h3 id="post__companies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[Company](#schemacompany)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="appointments-management-api-employees">employees</h1>

Companies employees

## get__employees_{id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/employees/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/employees/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/employees/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/employees/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/employees/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/employees/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/employees/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /employees/{id}`

*Returns single employee data*

Returns employee data identified by {id}

<h3 id="get__employees_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}
```

<h3 id="get__employees_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific employee|[Employee](#schemaemployee)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Employee not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__employees_{id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/v1/employees/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:3000/v1/employees/{id} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/employees/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/employees/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:3000/v1/employees/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:3000/v1/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/employees/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/v1/employees/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /employees/{id}`

*Updates employee information*

Updates employee data identified by {id} returning no information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}
```

<h3 id="put__employees_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Employee](#schemaemployee)|true|Contains employee information to be updated on the record, must contain all employee requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="put__employees_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Employee not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__employees

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/employees \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/employees HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/employees',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/employees',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/employees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/employees");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/employees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /employees`

*Returns company employee data*

Returns all company employees data

<h3 id="get__employees-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone": "string",
    "created_at": "2019-08-17T22:45:37Z",
    "permissions": {
      "add_employee": true,
      "update_client": true,
      "update_schedule": true
    }
  }
]
```

<h3 id="get__employees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company employee data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="get__employees-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Employee](#schemaemployee)]|false|none|none|
|» id|string|true|none|none|
|» name|string|true|none|none|
|» surname|string|true|none|none|
|» email|string|true|none|none|
|» phone|string|false|none|none|
|» created_at|string(date-time)|true|none|none|
|» permissions|[Employee_permissions](#schemaemployee_permissions)|true|none|none|
|»» add_employee|boolean|true|none|none|
|»» update_client|boolean|true|none|none|
|»» update_schedule|boolean|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__employees

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/v1/employees \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:3000/v1/employees HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/employees',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/employees',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:3000/v1/employees',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:3000/v1/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/employees");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/v1/employees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /employees`

*Creates new employee*

Creates new employee returning no information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}
```

<h3 id="post__employees-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Employee](#schemaemployee)|true|Contains employee information to be added to the record|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}
```

<h3 id="post__employees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[Employee](#schemaemployee)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="appointments-management-api-clients">clients</h1>

Companies clients

## get__clients_{id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/clients/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/clients/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/clients/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/clients/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}`

*Returns single client data*

Returns client data identified by {id}

<h3 id="get__clients_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}
```

<h3 id="get__clients_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific client|[Client](#schemaclient)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__clients_{id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/v1/clients/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:3000/v1/clients/{id} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients/{id}',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:3000/v1/clients/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:3000/v1/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/v1/clients/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /clients/{id}`

*Updates client information*

Updates client data identified by {id} returning no information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}
```

<h3 id="put__clients_{id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Client](#schemaclient)|true|Contains client information to be updated on the record, must contain all client requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="put__clients_{id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__clients_{id}_appointments

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/clients/{id}/appointments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/clients/{id}/appointments HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients/{id}/appointments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients/{id}/appointments',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/clients/{id}/appointments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients/{id}/appointments");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}/appointments`

*Returns client appointments or single appointment information*

Returns all client appointments or single appointment information information data. Client information is specified by path id and appointment information is provided by optional query parameter appointment_id

<h3 id="get__clients_{id}_appointments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|appointment_id|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "employee_id": "string",
    "client_id": "string",
    "created_at": "2019-08-17T22:45:37Z",
    "start_date": "2019-08-17T22:45:37Z",
    "end_date": "2019-08-17T22:45:37Z"
  }
]
```

<h3 id="get__clients_{id}_appointments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets array of with information of all client appointments or single appointment information if ?appointment_id is added to request. Client identified by {id}|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Appointments or appointment not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="get__clients_{id}_appointments-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## put__clients_{id}_appointments

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/v1/clients/{id}/appointments?appointment_id=string \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT http://localhost:3000/v1/clients/{id}/appointments?appointment_id=string HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients/{id}/appointments',
  method: 'put',
  data: '?appointment_id=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients/{id}/appointments?appointment_id=string',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put 'http://localhost:3000/v1/clients/{id}/appointments',
  params: {
  'appointment_id' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('http://localhost:3000/v1/clients/{id}/appointments', params={
  'appointment_id': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients/{id}/appointments?appointment_id=string");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/v1/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /clients/{id}/appointments`

*Updates appointment information*

Updates appointment data for client identified by {id} and appointment identified by ?appointment_id returning no information

> Body parameter

```json
{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}
```

<h3 id="put__clients_{id}_appointments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|appointment_id|query|string|true|none|
|body|body|[Appointment](#schemaappointment)|true|Contains appointment information to be updated on the record, must contain all appointment requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="put__clients_{id}_appointments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Update successful, no information returned|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Appointment not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__clients_{id}_appointments

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/v1/clients/{id}/appointments \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:3000/v1/clients/{id}/appointments HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients/{id}/appointments',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients/{id}/appointments',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:3000/v1/clients/{id}/appointments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:3000/v1/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients/{id}/appointments");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/v1/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /clients/{id}/appointments`

*Creates new appointment for client*

Creates new appointment returning new appointment information. Client identified by {id}

> Body parameter

```json
{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}
```

<h3 id="post__clients_{id}_appointments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Appointment](#schemaappointment)|true|Contains appointment information to be added to the record|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}
```

<h3 id="post__clients_{id}_appointments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[Appointment](#schemaappointment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## get__clients

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/v1/clients \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://localhost:3000/v1/clients HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://localhost:3000/v1/clients',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://localhost:3000/v1/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/v1/clients", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients`

*Returns company client data*

Returns all company clients data

<h3 id="get__clients-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone": "string",
    "created_at": "2019-08-17T22:45:37Z",
    "added_by": "string",
    "company_added": "string"
  }
]
```

<h3 id="get__clients-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array with client information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="get__clients-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Client](#schemaclient)]|false|none|none|
|» id|string|true|none|none|
|» name|string|true|none|none|
|» surname|string|true|none|none|
|» email|string|true|none|none|
|» phone|string|false|none|none|
|» created_at|string(date-time)|true|none|none|
|» added_by|string|true|none|none|
|» company_added|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## post__clients

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/v1/clients \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://localhost:3000/v1/clients HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://localhost:3000/v1/clients',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://localhost:3000/v1/clients',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://localhost:3000/v1/clients',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://localhost:3000/v1/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:3000/v1/clients");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/v1/clients", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /clients`

*Creates new client*

Creates new client returning new client information

> Body parameter

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}
```

<h3 id="post__clients-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[Client](#schemaclient)|true|Contains client information to be added to the record|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}
```

<h3 id="post__clients-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[Client](#schemaclient)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

# Schemas

<h2 id="tocSgeneralerror">GeneralError</h2>

<a id="schemageneralerror"></a>

```json
{
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|

<h2 id="tocSnotfounderror">NotFoundError</h2>

<a id="schemanotfounderror"></a>

```json
{
  "message": "string",
  "hint": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|
|hint|string|true|none|none|

<h2 id="tocSemployee">Employee</h2>

<a id="schemaemployee"></a>

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone|string|false|none|none|
|created_at|string(date-time)|true|none|none|
|permissions|[Employee_permissions](#schemaemployee_permissions)|true|none|none|

<h2 id="tocSclient">Client</h2>

<a id="schemaclient"></a>

```json
{
  "id": "string",
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "added_by": "string",
  "company_added": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone|string|false|none|none|
|created_at|string(date-time)|true|none|none|
|added_by|string|true|none|none|
|company_added|string|true|none|none|

<h2 id="tocScompany">Company</h2>

<a id="schemacompany"></a>

```json
{
  "id": "string",
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-17T22:45:37Z",
  "employees_id": [
    "string"
  ],
  "address": {
    "street": "string",
    "city": "string",
    "county": "string",
    "state": "string",
    "country": "string",
    "post_code": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|notification_advance|integer(int64)|false|none|none|
|created_at|string(date-time)|true|none|none|
|employees_id|[string]|false|none|none|
|address|[Company_address](#schemacompany_address)|true|none|none|

<h2 id="tocSappointment">Appointment</h2>

<a id="schemaappointment"></a>

```json
{
  "id": "string",
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-17T22:45:37Z",
  "start_date": "2019-08-17T22:45:37Z",
  "end_date": "2019-08-17T22:45:37Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|employee_id|string|true|none|none|
|client_id|string|true|none|none|
|created_at|string(date-time)|true|none|none|
|start_date|string(date-time)|true|none|none|
|end_date|string(date-time)|true|none|none|

<h2 id="tocSemployee_permissions">Employee_permissions</h2>

<a id="schemaemployee_permissions"></a>

```json
{
  "add_employee": true,
  "update_client": true,
  "update_schedule": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|add_employee|boolean|true|none|none|
|update_client|boolean|true|none|none|
|update_schedule|boolean|true|none|none|

<h2 id="tocScompany_address">Company_address</h2>

<a id="schemacompany_address"></a>

```json
{
  "street": "string",
  "city": "string",
  "county": "string",
  "state": "string",
  "country": "string",
  "post_code": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|street|string|true|none|none|
|city|string|true|none|none|
|county|string|false|none|none|
|state|string|false|none|none|
|country|string|true|none|none|
|post_code|integer|true|none|none|

