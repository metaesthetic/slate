---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the American Icarus  API documentation. You can use our API to access American Icarus cartographic API endpoints, which can get information on various geolocations, routes, and excerpts from the novel **American Icarus** by jason hoyt.

We have language bindings in Shell and Javascript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Authentication

> To authorize, use this code:

```ruby
require 'americanicarus'

api = AI::APIClient.authorize!('i.am.icarus')
```

```python
import americanicarus 

api = americanicarus.authorize('i.am.icarus')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: i.am.icarus"
```

```javascript
const location = require('americanicarus');

let api = location.authorize('i.am.icarus');
```

> Make sure to replace `i.am.icarus` with your API key.

americanicarus uses API keys to allow access to the API. You can register a new American Icarus Authentication API key at our [developer portal](http://example.com/developers).

americanicarus expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: i.am.icarus`

<aside class="notice">
You must replace <code>i.am.icarus</code> with your personal API key.
</aside>

# Locations

## Get All Locations

```ruby
require 'americanicarus'

api = AI::APIClient.authorize!('i.am.icarus')
api.locations.get
```

```python
import americanicarus 

api = americanicarus.authorize('i.am.icarus')
api.locations.get()
```

```shell
curl "https://api.americanicarus.com/locations"
  -H "Authorization: i.am.icarus"
```

```javascript
const location = require('location');

let api = location.authorize('i.am.icarus');
let locations = api.locations.get();
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

This endpoint retrieves all locations.

### HTTP Request

`GET https://api.americanicarus.com/locations`


<aside class="success">
Remember — a happy icarus is an authenticated location!
</aside>

## Get a Specific location

```ruby
require 'americanicarus'

api = AI::APIClient.authorize!('i.am.icarus')
api.locations.get(2)
```

```python
import location 

api = location.authorize('i.am.icarus')
api.locations.get(2)
```

```shell
curl "https://api.americanicarus.com/locations/2"
  -H "Authorization: i.am.icarus"
```

```javascript
const location = require('location');

let api = location.authorize('i.am.icarus');
let max = api.locations.get(2);
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

This endpoint retrieves a specific location.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://api.americanicarus.com/locations/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the location to retrieve

