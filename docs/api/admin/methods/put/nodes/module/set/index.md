---
layout: api
title: PUT /nodes/:module/:set
---

Enable/Disable a node set

### Headers

Header          | Value
----------------|-------
`Authorization` | `Bearer [token]` - if authentication is enabled
`Content-type`  | `application/json`


### Arguments

Path Component | Description
---------------|------------
`module`       | The name of the module 
`set`          | The name of the set

The request body must be a JSON string with the following fields:

Field     | Description
----------|------------------------
`enabled` | `true` or `false` - whether to enable or disable the module

    {
      "enabled": true
    }

### Response

Status Code | Reason         | Response
------------|----------------|--------------
`200`       | Success        | A [Node Set](/docs/api/admin/types.html#node-module) object. See example response body
`400`       | Bad request    | An [Error response](/docs/api/admin/errors.html)
`401`       | Not authorized | _none_
`404`       | Not found      | _none_


    {
      "id": "node-red-node-suncalc/suncalc",
      "name": "suncalc",
      "types": [
        "sunrise"
      ],
      "enabled": false,
      "module": "node-red-node-suncalc"
    }

