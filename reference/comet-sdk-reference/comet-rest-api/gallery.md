---
description: View a user's gallery without talking to an RPC node.
---

# Gallery

## Get Gallery

{% swagger method="get" path="/gallery" baseUrl="https://api.withcomet.com/v1" summary="Gets all tokens owned by a user or address." expanded="true" %}
{% swagger-description %}
One of 

`address`

 or 

`userId`

 is required.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="address" %}
Solana address
{% endswagger-parameter %}

{% swagger-parameter in="query" name="userId" %}
Comet User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```json
{
    "gallery": [
        {
            "id": "c78568a5d18ece391150e54309abadea",
            "createdAt": "2022-08-17T13:24:49-07:00",
            "mintPubkey": "3papQrFrW9ciBZw9AJZLoaMgEgWGR7cm6Tj3bkjWjPAU",
            "edition": "0",
            "uri": "https://api-dev.withcomet.com/comet/token/32f8aa684bd5/metadata/0",
            "mintStatus": "mint_succeeded"
        },
        {
            "id": "77cee9957118549f545d99942762620d",
            "createdAt": "2022-09-20T11:41:19-07:00",
            "mintPubkey": "8DZNB2oNqThWZZaVZKNEx7VtiXefvTQatRWjpZzGFhtB",
            "edition": "1",
            "uri": "https://api-dev.withcomet.com/comet/token/fdfbdb5ddeaf/metadata/1",
            "mintStatus": "mint_succeeded"
        },
        {
            "id": "bb71d468a5f7ad4734aa2b426365cd6b",
            "createdAt": "2022-09-20T11:42:48-07:00",
            "mintPubkey": "3yUwDEFUDkm5VjW5e6o9ckMD4MtvTH8v3mrM13MdM7DY",
            "edition": "1",
            "uri": "https://api-dev.withcomet.com/comet/token/fe3d525cee27/metadata/1",
            "mintStatus": "mint_succeeded"
        },
        {
            "id": "486ad5d90e33f96ba0f04837f2d0f18a",
            "createdAt": "2022-12-21T21:42:47-08:00",
            "mintPubkey": "BGT9r9B8pwKtSU7NgxhYKQbBbstdXi7q1JTizZRp7QKg",
            "edition": "2",
            "uri": "https://api-dev.withcomet.com/comet/token/56bf8813ff67/metadata/2",
            "mintStatus": "mint_succeeded"
        },
        {
            "id": "6c6ba2001a5f88b01c5dfd1e9ad5d472",
            "createdAt": "2022-10-05T13:39:21-07:00",
            "mintPubkey": "J9fMFnawKkf4MzpDnf47B6fJJedEeH8D3pyXVRwbX66Q",
            "edition": "1",
            "uri": "https://api-dev.withcomet.com/comet/token/9e7b5fc982c8/metadata/1",
            "mintStatus": "mint_succeeded"
        }
    ]
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

