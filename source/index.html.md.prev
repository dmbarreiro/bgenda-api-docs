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

<h1 id="appointments-management-api">Appointments management API v0.5</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Specification for appointment management service with notifications

Base URLs:

* <a href="https://localhost:3000/v1.0/">https://localhost:3000/v1.0/</a>

Email: <a href="mailto:david@dmbarreiro.com">David Martinez Barreiro</a> Web: <a href="https://www.dmbarreiro.com">David Martinez Barreiro</a> 
 License: All Rights Reserved

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **api_key**, in: header. 

- HTTP Authentication, scheme: basic 

- HTTP Authentication, scheme: bearer 

<h1 id="appointments-management-api-companies">companies</h1>

Companies using appointments service

## getCompanyById

<a id="opIdgetCompanyById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/companies/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/companies/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/companies/{id}',
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

fetch('https://localhost:3000/v1.0/companies/{id}',
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

result = RestClient.get 'https://localhost:3000/v1.0/companies/{id}',
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

r = requests.get('https://localhost:3000/v1.0/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies/{id}");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/companies/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}`

*Returns single company information*

Returns company information identified by {id}

<h3 id="getcompanybyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
  },
  "id": "string"
}
```

<h3 id="getcompanybyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific company|[RegisteredCompany](#schemaregisteredcompany)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Company not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateCompanyById

<a id="opIdupdateCompanyById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://localhost:3000/v1.0/companies/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://localhost:3000/v1.0/companies/{id} HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/companies/{id}',
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
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
  },
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/companies/{id}',
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

result = RestClient.put 'https://localhost:3000/v1.0/companies/{id}',
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

r = requests.put('https://localhost:3000/v1.0/companies/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies/{id}");
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
    req, err := http.NewRequest("PUT", "https://localhost:3000/v1.0/companies/{id}", data)
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
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
  },
  "id": "string"
}
```

<h3 id="updatecompanybyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|
|body|body|[RegisteredCompany](#schemaregisteredcompany)|true|Contains company information to be updated on the record, must contain all company requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="updatecompanybyid-responses">Responses</h3>

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

## getCompanyEmployees

<a id="opIdgetCompanyEmployees"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/companies/{id}/employees \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/companies/{id}/employees HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/companies/{id}/employees',
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

fetch('https://localhost:3000/v1.0/companies/{id}/employees',
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

result = RestClient.get 'https://localhost:3000/v1.0/companies/{id}/employees',
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

r = requests.get('https://localhost:3000/v1.0/companies/{id}/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies/{id}/employees");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/companies/{id}/employees", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}/employees`

*Returns company employee data*

Returns all company employees data

<h3 id="getcompanyemployees-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone": "string",
    "created_at": "2019-08-20T20:25:56Z",
    "permissions": {
      "add_employee": true,
      "update_client": true,
      "update_schedule": true
    },
    "id": "string"
  }
]
```

<h3 id="getcompanyemployees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company employee data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanyemployees-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|
|»» name|string|true|none|none|
|»» surname|string|true|none|none|
|»» email|string|true|none|none|
|»» phone|string|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» permissions|[BasicEmployee_permissions](#schemabasicemployee_permissions)|true|none|none|
|»»» add_employee|boolean|true|none|none|
|»»» update_client|boolean|true|none|none|
|»»» update_schedule|boolean|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» id|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getCompanyClients

<a id="opIdgetCompanyClients"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/companies/{id}/clients \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/companies/{id}/clients HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/companies/{id}/clients',
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

fetch('https://localhost:3000/v1.0/companies/{id}/clients',
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

result = RestClient.get 'https://localhost:3000/v1.0/companies/{id}/clients',
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

r = requests.get('https://localhost:3000/v1.0/companies/{id}/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies/{id}/clients");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/companies/{id}/clients", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies/{id}/clients`

*Returns company client data*

Returns all company clients data

<h3 id="getcompanyclients-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Company id|

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "surname": "string",
    "email": "string",
    "phone": "string",
    "created_at": "2019-08-20T20:25:56Z",
    "added_by": "string",
    "company_added": "string",
    "id": "string"
  }
]
```

<h3 id="getcompanyclients-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array with client information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanyclients-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicClient](#schemabasicclient)|false|none|none|
|»» name|string|true|none|none|
|»» surname|string|true|none|none|
|»» email|string|true|none|none|
|»» phone|string|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» added_by|string|true|none|none|
|»» company_added|string|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» id|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## getCompanies

<a id="opIdgetCompanies"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/companies \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/companies HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/companies',
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

fetch('https://localhost:3000/v1.0/companies',
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

result = RestClient.get 'https://localhost:3000/v1.0/companies',
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

r = requests.get('https://localhost:3000/v1.0/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/companies", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /companies`

*Returns information from all companies*

Returns an array with information from each company

> Example responses

> 200 Response

```json
[
  {
    "name": "string",
    "notification_advance": 0,
    "created_at": "2019-08-20T20:25:56Z",
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
    },
    "id": "string"
  }
]
```

<h3 id="getcompanies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns array of company information data|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getcompanies-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|
|»» name|string|true|none|none|
|»» notification_advance|integer(int64)|false|none|none|
|»» created_at|string(date-time)|true|none|none|
|»» employees_id|[string]|false|none|none|
|»» address|[BasicCompany_address](#schemabasiccompany_address)|true|none|none|
|»»» street|string|true|none|none|
|»»» city|string|true|none|none|
|»»» county|string|false|none|none|
|»»» state|string|false|none|none|
|»»» country|string|true|none|none|
|»»» post_code|integer|true|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» id|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createCompany

<a id="opIdcreateCompany"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://localhost:3000/v1.0/companies \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://localhost:3000/v1.0/companies HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/companies',
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
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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

fetch('https://localhost:3000/v1.0/companies',
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

result = RestClient.post 'https://localhost:3000/v1.0/companies',
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

r = requests.post('https://localhost:3000/v1.0/companies', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/companies");
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
    req, err := http.NewRequest("POST", "https://localhost:3000/v1.0/companies", data)
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
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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

<h3 id="createcompany-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicCompany](#schemabasiccompany)|true|Contains company information to be added to the record|

> Example responses

> 201 Response

```json
{
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
  },
  "id": "string"
}
```

<h3 id="createcompany-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[RegisteredCompany](#schemaregisteredcompany)|
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

## getEmployeeById

<a id="opIdgetEmployeeById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/employees/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/employees/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/employees/{id}',
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

fetch('https://localhost:3000/v1.0/employees/{id}',
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

result = RestClient.get 'https://localhost:3000/v1.0/employees/{id}',
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

r = requests.get('https://localhost:3000/v1.0/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/employees/{id}");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/employees/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /employees/{id}`

*Returns single employee data*

Returns employee data identified by {id}

<h3 id="getemployeebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Employee id|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  },
  "id": "string"
}
```

<h3 id="getemployeebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific employee|[RegisteredEmployee](#schemaregisteredemployee)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Employee not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateEmployeeById

<a id="opIdupdateEmployeeById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://localhost:3000/v1.0/employees/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://localhost:3000/v1.0/employees/{id} HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/employees/{id}',
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  },
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/employees/{id}',
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

result = RestClient.put 'https://localhost:3000/v1.0/employees/{id}',
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

r = requests.put('https://localhost:3000/v1.0/employees/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/employees/{id}");
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
    req, err := http.NewRequest("PUT", "https://localhost:3000/v1.0/employees/{id}", data)
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  },
  "id": "string"
}
```

<h3 id="updateemployeebyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[RegisteredEmployee](#schemaregisteredemployee)|true|Contains employee information to be updated on the record, must contain all employee requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="updateemployeebyid-responses">Responses</h3>

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

## createEmployee

<a id="opIdcreateEmployee"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://localhost:3000/v1.0/employees \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://localhost:3000/v1.0/employees HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/employees',
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
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

fetch('https://localhost:3000/v1.0/employees',
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

result = RestClient.post 'https://localhost:3000/v1.0/employees',
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

r = requests.post('https://localhost:3000/v1.0/employees', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/employees");
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
    req, err := http.NewRequest("POST", "https://localhost:3000/v1.0/employees", data)
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  }
}
```

<h3 id="createemployee-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicEmployee](#schemabasicemployee)|true|Contains employee information to be added to the record|

> Example responses

> 201 Response

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  },
  "id": "string"
}
```

<h3 id="createemployee-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[RegisteredEmployee](#schemaregisteredemployee)|
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

## getClientById

<a id="opIdgetClientById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/clients/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/clients/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/clients/{id}',
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

fetch('https://localhost:3000/v1.0/clients/{id}',
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

result = RestClient.get 'https://localhost:3000/v1.0/clients/{id}',
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

r = requests.get('https://localhost:3000/v1.0/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients/{id}");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/clients/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}`

*Returns single client data*

Returns client data identified by {id}

<h3 id="getclientbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string",
  "id": "string"
}
```

<h3 id="getclientbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets the specific client|[RegisteredClient](#schemaregisteredclient)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Client not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateClientById

<a id="opIdupdateClientById"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://localhost:3000/v1.0/clients/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://localhost:3000/v1.0/clients/{id} HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/clients/{id}',
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string",
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/clients/{id}',
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

result = RestClient.put 'https://localhost:3000/v1.0/clients/{id}',
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

r = requests.put('https://localhost:3000/v1.0/clients/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients/{id}");
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
    req, err := http.NewRequest("PUT", "https://localhost:3000/v1.0/clients/{id}", data)
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string",
  "id": "string"
}
```

<h3 id="updateclientbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[RegisteredClient](#schemaregisteredclient)|true|Contains client information to be updated on the record, must contain all client requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="updateclientbyid-responses">Responses</h3>

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

## getClientAppointment

<a id="opIdgetClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://localhost:3000/v1.0/clients/{id}/appointments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://localhost:3000/v1.0/clients/{id}/appointments HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://localhost:3000/v1.0/clients/{id}/appointments',
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

fetch('https://localhost:3000/v1.0/clients/{id}/appointments',
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

result = RestClient.get 'https://localhost:3000/v1.0/clients/{id}/appointments',
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

r = requests.get('https://localhost:3000/v1.0/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients/{id}/appointments");
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
    req, err := http.NewRequest("GET", "https://localhost:3000/v1.0/clients/{id}/appointments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /clients/{id}/appointments`

*Returns client appointments or single appointment information*

Returns all client appointments or single appointment information information data. Client information is specified by path id and appointment information is provided by optional query parameter appointment_id

<h3 id="getclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|appointment_id|query|string|false|Appointment resource identified|

> Example responses

> 200 Response

```json
[
  {
    "employee_id": "string",
    "client_id": "string",
    "created_at": "2019-08-20T20:25:56Z",
    "start_date": "2019-08-20T20:25:56Z",
    "end_date": "2019-08-20T20:25:56Z",
    "id": "string"
  }
]
```

<h3 id="getclientappointment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Gets array of with information of all client appointments or single appointment information if ?appointment_id is added to request. Client identified by {id}|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Appointments or appointment not found|[NotFoundError](#schemanotfounderror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<h3 id="getclientappointment-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## updateClientAppointment

<a id="opIdupdateClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT https://localhost:3000/v1.0/clients/{id}/appointments?appointment_id=string \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://localhost:3000/v1.0/clients/{id}/appointments?appointment_id=string HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/clients/{id}/appointments',
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
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z",
  "id": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/clients/{id}/appointments?appointment_id=string',
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

result = RestClient.put 'https://localhost:3000/v1.0/clients/{id}/appointments',
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

r = requests.put('https://localhost:3000/v1.0/clients/{id}/appointments', params={
  'appointment_id': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients/{id}/appointments?appointment_id=string");
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
    req, err := http.NewRequest("PUT", "https://localhost:3000/v1.0/clients/{id}/appointments", data)
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
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z",
  "id": "string"
}
```

<h3 id="updateclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|appointment_id|query|string|true|Appointment resource identified|
|body|body|[RegisteredAppointment](#schemaregisteredappointment)|true|Contains appointment information to be updated on the record, must contain all appointment requested fields|

> Example responses

> 400 Response

```json
{
  "message": "string"
}
```

<h3 id="updateclientappointment-responses">Responses</h3>

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

## createClientAppointment

<a id="opIdcreateClientAppointment"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://localhost:3000/v1.0/clients/{id}/appointments \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://localhost:3000/v1.0/clients/{id}/appointments HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/clients/{id}/appointments',
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
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/clients/{id}/appointments',
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

result = RestClient.post 'https://localhost:3000/v1.0/clients/{id}/appointments',
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

r = requests.post('https://localhost:3000/v1.0/clients/{id}/appointments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients/{id}/appointments");
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
    req, err := http.NewRequest("POST", "https://localhost:3000/v1.0/clients/{id}/appointments", data)
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
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z"
}
```

<h3 id="createclientappointment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Client id|
|body|body|[BasicAppointment](#schemabasicappointment)|true|Contains appointment information to be added to the record|

> Example responses

> 201 Response

```json
{
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z",
  "id": "string"
}
```

<h3 id="createclientappointment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[RegisteredAppointment](#schemaregisteredappointment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Request does not have the right format or missing required data|[GeneralError](#schemageneralerror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated|[GeneralError](#schemageneralerror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Permission denied|[GeneralError](#schemageneralerror)|
|default|Default|Error|[GeneralError](#schemageneralerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## createClient

<a id="opIdcreateClient"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://localhost:3000/v1.0/clients \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://localhost:3000/v1.0/clients HTTP/1.1
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
  url: 'https://localhost:3000/v1.0/clients',
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://localhost:3000/v1.0/clients',
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

result = RestClient.post 'https://localhost:3000/v1.0/clients',
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

r = requests.post('https://localhost:3000/v1.0/clients', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://localhost:3000/v1.0/clients");
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
    req, err := http.NewRequest("POST", "https://localhost:3000/v1.0/clients", data)
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
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string"
}
```

<h3 id="createclient-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BasicClient](#schemabasicclient)|true|Contains client information to be added to the record|

> Example responses

> 201 Response

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string",
  "id": "string"
}
```

<h3 id="createclient-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Resource created successfully, created resource is returned|[RegisteredClient](#schemaregisteredclient)|
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

<h2 id="tocSregisteredemployee">RegisteredEmployee</h2>

<a id="schemaregisteredemployee"></a>

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "permissions": {
    "add_employee": true,
    "update_client": true,
    "update_schedule": true
  },
  "id": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicEmployee](#schemabasicemployee)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|true|none|none|

<h2 id="tocSbasicemployee">BasicEmployee</h2>

<a id="schemabasicemployee"></a>

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
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
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone|string|false|none|none|
|created_at|string(date-time)|true|none|none|
|permissions|[BasicEmployee_permissions](#schemabasicemployee_permissions)|true|none|none|

<h2 id="tocSregisteredclient">RegisteredClient</h2>

<a id="schemaregisteredclient"></a>

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string",
  "id": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicClient](#schemabasicclient)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|true|none|none|

<h2 id="tocSbasicclient">BasicClient</h2>

<a id="schemabasicclient"></a>

```json
{
  "name": "string",
  "surname": "string",
  "email": "string",
  "phone": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "added_by": "string",
  "company_added": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|surname|string|true|none|none|
|email|string|true|none|none|
|phone|string|false|none|none|
|created_at|string(date-time)|true|none|none|
|added_by|string|true|none|none|
|company_added|string|true|none|none|

<h2 id="tocSregisteredcompany">RegisteredCompany</h2>

<a id="schemaregisteredcompany"></a>

```json
{
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
  },
  "id": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicCompany](#schemabasiccompany)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|true|none|none|

<h2 id="tocSbasiccompany">BasicCompany</h2>

<a id="schemabasiccompany"></a>

```json
{
  "name": "string",
  "notification_advance": 0,
  "created_at": "2019-08-20T20:25:56Z",
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
|name|string|true|none|none|
|notification_advance|integer(int64)|false|none|none|
|created_at|string(date-time)|true|none|none|
|employees_id|[string]|false|none|none|
|address|[BasicCompany_address](#schemabasiccompany_address)|true|none|none|

<h2 id="tocSregisteredappointment">RegisteredAppointment</h2>

<a id="schemaregisteredappointment"></a>

```json
{
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z",
  "id": "string"
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[BasicAppointment](#schemabasicappointment)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|true|none|none|

<h2 id="tocSbasicappointment">BasicAppointment</h2>

<a id="schemabasicappointment"></a>

```json
{
  "employee_id": "string",
  "client_id": "string",
  "created_at": "2019-08-20T20:25:56Z",
  "start_date": "2019-08-20T20:25:56Z",
  "end_date": "2019-08-20T20:25:56Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|employee_id|string|true|none|none|
|client_id|string|true|none|none|
|created_at|string(date-time)|true|none|none|
|start_date|string(date-time)|true|none|none|
|end_date|string(date-time)|true|none|none|

<h2 id="tocSbasicemployee_permissions">BasicEmployee_permissions</h2>

<a id="schemabasicemployee_permissions"></a>

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

<h2 id="tocSbasiccompany_address">BasicCompany_address</h2>

<a id="schemabasiccompany_address"></a>

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

