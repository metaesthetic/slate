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
    "_id": "57c7a6aba130ac4b8538bc0b",
    "id": "1",
    "title": "father's gravemarker",
    "description": "",
    "excerpt": "Leaving the circumference of the metallic ride behind I head for the graveyard on the other side of the small town. It is the place were we held father’s funeral in abstentia; his body never found. It’s autumn but soon the first snows will begin to fall and nobody will be able to read his name easily. Nobody will come visit his grave marker this year. ",
    "longitude": "-85.352223",
    "latitude": "42.954655",
    "camera": {
      "center": [
        -85.352223,
        42.954655
      ],
      "bearing": 36,
      "zoom": 15,
      "speed": 0.8
    }
  },
  {
    "_id": "57c7a6c5a130ac4b8538bc0c",
    "id": "2",
    "title": "Hermon Dunlop Smith Center for Cartography",
    "description": "",
    "excerpt": "I was there to see a map, however, a very, very special map. The one that gave America its name. The fourth part of the world, drawn as it’s own continent, was baptized by a German Cartographer, Waldseemüller, who possessed epic vision and skill. This was America’s Confirmation, and I aimed to see it on this journey.",
    "longitude": "-87.630618",
    "latitude": "41.900012",
    "camera": {
      "center": [
        -87.630618,
        41.900012
      ],
      "bearing": 20,
      "pitch": 60,
      "zoom": 15,
      "speed": 0.8
    }
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
curl "https://api.americanicarus.com/locations/57c7a6f3a130ac4b8538bc10"
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
  "_id": "57c7a6f3a130ac4b8538bc10",
  "id": "6",
  "title": "The Statue of Junipero Serra",
  "description": "",
  "excerpt": "He loomed large, but was comically sculpted as if a child cast him in silly putty. He pointed west and even a bit downward into the valley. I wondered if he was pointing towards the old resort town of Crystal Springs, now drowned completely by the waters. She told me how some friends of hers had hung an enormous sign from his finger, 'pull it', it had said.",
  "longitude": "-122.363445",
  "latitude": "37.538479",
  "camera": {
    "center": [
      -122.363445,
      37.538479
    ],
    "bearing": -50,
    "pitch": 7,
    "zoom": 16,
    "speed": 1
  }
}
```

This endpoint retrieves a specific location.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://api.americanicarus.com/locations/<_id>`

### URL Parameters

Parameter | Description
--------- | -----------
_id | The _id of the location to retrieve

