# Airdrop

## Airdrop Status

{% swagger method="get" path="/airdrop/:id" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets status of airdrops." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="path" required="true" %}
id of airdrop
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    "id": "I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U",
    "statuses": {
        "SUCCEEDED": [
            {
                "taskId": "a64445c3866c7080549051276f289937",
                "CometUserId": "c4367732ab0c",
                "address": "2yAEzsC4GPCT3kGq39K5KLAqPFo4xzvNShDZHqCWo4Gx"
            },
            {
                "taskId": "37e44b47a52368a95bc7a0b2170e2e5f",
                "CometUserId": null,
                "address": "AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy"
            }
        ]
    },
    "count": 2
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Deploy Airdrop

<details>

<summary>Example Request Body</summary>

```
{
  "sequential": false,
  "airdrops": [
    { "collectionId": "9f46cddbd46f", "address": "AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy" },
    { "collectionId": "9f46cddbd46f", "userId": "c4367732ab0c" }
  ] 
}
```

</details>

{% swagger method="post" path="/airdrop" baseUrl="https://api.withcomet.com/rest/v1" summary="Deploys airdrops." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="airdrops" required="true" %}
list of airdrops to deploy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sequential" type="Boolean" %}
whether or not to batch airdrops in groups of 10
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    "id": "I4WTgq6ZHb2ncugUWBz1oSPDld5eJi5U",
    "count": 2
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
