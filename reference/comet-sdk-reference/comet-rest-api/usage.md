---
description: Get your API usage history.
---

# Usage

## Get API usage

{% swagger method="get" path="/usage" baseUrl="https://api.withcomet.com/v1" summary="Gets API usage." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
  "requests":[
    {
      "path":"/rest/v1/airdrop/",
      "method":"POST",
      "request":{
        "body":{
          "airdrops":[
            {
              "address":"AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy",
              "collectionId":"9f46cddbd46f"
            },
            {
              "userId":"c4367732ab0c",
              "collectionId":"9f46cddbd46f"
            }
          ],
          "sequential":false
        },
        "query":{
          
        },
        "params":{
          
        },
        "headers":{
          "host":"localhost:9000",
          "accept":"*/*",
          "connection":"keep-alive",
          "user-agent":"PostmanRuntime/7.29.2",
          "content-type":"application/json",
          "authorization":"Bearer IncYP3edd3blm2ypLGFFOYwQsC5vff3n",
          "postman-token":"bb58f535-a047-4a0d-af7b-dbb078d0da0c",
          "content-length":"220",
          "accept-encoding":"gzip, deflate, br"
        }
      },
      "response":{
        "id":"I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U",
        "count":2
      },
      "status":200,
      "createdAt":"2023-01-11T08:03:53.020Z"
    },
    {
      "path":"/rest/v1/airdrop/I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U",
      "method":"GET",
      "request":{
        "body":{
          
        },
        "query":{
          
        },
        "params":{
          "batchId":"I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U"
        },
        "headers":{
          "host":"localhost:9000",
          "accept":"*/*",
          "connection":"keep-alive",
          "user-agent":"PostmanRuntime/7.29.2",
          "authorization":"Bearer IncYP3edd3blm2ypLGFFOYwQsC5vff3n",
          "postman-token":"7ab5a826-d078-4180-9999-1f0b0590a10a",
          "accept-encoding":"gzip, deflate, br"
        }
      },
      "response":{
        "id":"I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U",
        "count":2,
        "statuses":{
          "SUCCEEDED":[
            {
              "taskId":"a64445c3866c7080549051276f289937",
              "address":"2yAEzsC4GPCT3kGq39K5KLAqPFo4xzvNShDZHqCWo4Gx",
              "CometUserId":"c4367732ab0c"
            },
            {
              "taskId":"37e44b47a52368a95bc7a0b2170e2e5f",
              "address":"AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy",
              "CometUserId":null
            }
          ]
        }
      },
      "status":200,
      "createdAt":"2023-01-11T08:07:39.839Z"
    },
    {
      "path":"/rest/v1/collection/098f868479eb/owners",
      "method":"GET",
      "request":{
        "body":{
          
        },
        "query":{
          
        },
        "params":{
          "tokenDefinitionId":"098f868479eb"
        },
        "headers":{
          "host":"localhost:9000",
          "accept":"*/*",
          "connection":"keep-alive",
          "user-agent":"PostmanRuntime/7.29.2",
          "authorization":"Bearer IncYP3edd3blm2ypLGFFOYwQsC5vff3n",
          "postman-token":"4d8cfb24-cf03-4a85-b430-e6247823a599",
          "accept-encoding":"gzip, deflate, br"
        }
      },
      "response":{
        "results":{
          "owners":[
            
          ]
        }
      },
      "status":200,
      "createdAt":"2023-01-11T08:09:07.155Z"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}
