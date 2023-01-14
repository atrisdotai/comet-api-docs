# Airdrops

## Launch Airdrop

You can quickly distribute tokens from collections you've launched with Comet by using the `POST /airdrop` API endpoint. You'll need to specify a list of recipients (either their Comet User IDs or Solana addresses), and for each recipient indicate which collection you want them to receive. An example request is below.

After you've launched your airdrop, Comet will return an `id` that you can use to monitor the status of the airdrop.

{% hint style="warning" %}
Keep in mind that you cannot mint any collection past its `maxSupply`, when applicable. If you try to airdrop more NFTs from a collection than there are available tokens, some recipients won't receive the airdrop.
{% endhint %}

{% hint style="warning" %}
Even if your NFT collection requires payment, recipients will receive your airdropped NFTs for free.
{% endhint %}

<details>

<summary>Example Request Body</summary>

```
{
  "airdrops": [
    { "collectionId": "9f46cddbd46f", "address": "AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy" },
    { "collectionId": "9f46cddbd46f", "userId": "c4367732ab0c" }
  ] 
}
```

</details>

{% swagger method="post" path="/airdrop" baseUrl="https://api.withcomet.com/v1" summary="Send tokens to many users." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="airdrops" required="true" %}
List of recipients, specifying which collection each will receive.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer token
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

## Check Airdrop Status

{% swagger method="get" path="/airdrop/:id" baseUrl="https://api.withcomet.com/v1" summary="Get the status of a previously launched airdrop." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
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
