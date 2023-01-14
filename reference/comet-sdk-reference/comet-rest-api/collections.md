---
description: Launch and monitor NFT collections and their owners.
---

# Collections

## Create Collection

Launch an NFT collection on Solana mainnet. We currently support two types:

* **Static passes:** All NFTs in a static pass collection have the same image.
* **Numbered passes:** Like static passes, numbered passes all share the same image, but NFTs are distinguishable by a number at the bottom of the image. NFTs are minted in order, where the first NFT minted says "#1" at the bottom.

After calling this endpoint, Comet will automatically start deploying the collection on Solana mainnet. This usually takes 30-60 seconds. To monitor the progress of the deployment, use the `GET /collection` endpoint below.

{% hint style="info" %}
Note: This endpoint requires an image upload, so the request should be in the form of `multipart/form-data`.
{% endhint %}

{% swagger method="post" path="/collection" baseUrl="https://api.withcomet.com/v1" summary="Create a new NFT collection on Solana mainnet." expanded="true" %}
{% swagger-description %}
This endpoint requires an image upload, so the request should be in the form of 

`multipart/form-data`

.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer token with your Comet API key
{% endswagger-parameter %}

{% swagger-parameter in="body" name="backgroundUpload" type="File" required="true" %}
Uploaded via 

`multipart/form-data`

 request. An image file (JPG, or PNG) that will be displayed on all NFTs in the collection.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="String" required="true" %}
The name of the collection.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="symbol" type="String" required="true" %}
The symbol of the collection.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" required="true" %}
The description of the collection.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="subtype" type="String" %}
`numbered_pass` (default): the edition number will be displayed at the bottom of the NFT image.



`static_pass`: the edition number will not be shown on the NFT, only the uploaded image.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pricingModel" type="String" %}
`pay_once` (default): This NFT requires a one-time payment to be minted by a user.



`free`: This NFT is free to mint for anyone.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="Float" %}
If 

`pricingModel`

 is 

`pay_once`

, the price that users will need to pay to mint this NFT, in $USD.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="infiniteSupply" type="Boolean" %}
If `true`, this collection has an infinite number of tokens.



If `false` (default), the `maxSupply` parameter must be supplied.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="maxSupply" type="Integer" %}
If 

`infiniteSupply`

 is 

`false`

, the maximum number of tokens that can be minted from this collection.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```json
{
  "id": "6c2715377717",
  "name": "my test collection",
  "symbol": "TEST",
  "type": "milky_way_nft",
  "chainType": "solana",
  "chainId": 101,
  "subtype": "numbered_pass",
  "description": "whats good",
  "infiniteSupply": false,
  "maxSupply": 100,
  "price": 10,
  "pricingModel": "pay_once",
  "deployed": false,
  "isCometToken": true,
  "backgroundUpload": "OxnAlTCm9se8sMlnu0CeExmawJ0YVFGd4WcVgUCs3ZCfPbNm7NT9ewIfNKRfCgj7"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Invalid payload" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Get Launched Collections

{% swagger method="get" path="/collection" baseUrl="https://api.withcomet.com/v1" summary="Get a list of collections you've launched." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```json
{
  "collections": [
    {
      "id": "0c658cfcb4fb",
      "name": "apitest",
      "symbol": "API",
      "type": "milky_way_nft",
      "chainType": "solana",
      "chainId": 101,
      "subtype": "numbered_pass",
      "description": "hello folks",
      "infiniteSupply": false,
      "maxSupply": 100,
      "price": 10,
      "pricingModel": "pay_once",
      "deployed": true,
      "isCometToken": true,
      "backgroundUpload": "ZoYxhPO9miNsTq2wUcfTYT0Y2JbYdNUxwaunnW8CnIeAs9A4gDELT9C3xUM4zsJZ"
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Definition does not exist" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Get Collection by ID

{% swagger method="get" path="/collection/:id" baseUrl="https://api.withcomet.com/v1" summary="Retrieve a collection given its ID." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "id": "0c658cfcb4fb",
  "name": "apitest",
  "symbol": "API",
  "type": "milky_way_nft",
  "chainType": "solana",
  "chainId": 101,
  "subtype": "numbered_pass",
  "description": "hello folks",
  "infiniteSupply": false,
  "maxSupply": 100,
  "price": 10,
  "pricingModel": "pay_once",
  "deployed": true,
  "isCometToken": true,
  "backgroundUpload": "ZoYxhPO9miNsTq2wUcfTYT0Y2JbYdNUxwaunnW8CnIeAs9A4gDELT9C3xUM4zsJZ"
}
```
{% endswagger-response %}
{% endswagger %}

## Get Collection Holders

For a given collection, return a list of the Comet users and/or addresses who hold tokens in that collection.

{% swagger method="get" path="/collection/:id/holders" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets a collection's holders." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="path" name="collectionId" %}
id of collection
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    "holders": [
        {
            "address": {
                "chainType": "solana",
                "chainId": 103,
                "address": "EjLfGufWW47Rfc4mUxpwabGaoDCdqpSPsD3jVACxNSRE",
                "primary": true,
                "createdAt": "2022-06-18T03:11:11.873Z",
                "id": "481f11ba98c8"
            },
            "user": {
                "id": "efd61df49255",
                "username": "alexander",
                "addresses": [],
                "profile": {
                    "profilePictureKey": "xCnzCVFlJORryrZCreFsmtZuUxxNcSJGVKmWva7ffkNmSb7rGyWOVTy3478kNNEw"
                }
            }
        },
        {
            "address": {
                "chainType": "solana",
                "chainId": 103,
                "address": "AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy",
                "primary": true,
                "createdAt": "2022-08-17T20:24:26.627Z",
                "id": "1a6f2b51ad80"
            },
            "user": {
                "id": "da792fee8f1c",
                "username": "sabina",
                "addresses": [],
                "profile": {
                    "profilePictureKey": "AbWZwbpnaHBWBIs85cpF6zekYDGeD0SsiqHoEPwM2OTqeUZk9ydjvKM1JXeSIeJt"
                }
            }
        },
        {
            "address": {
                "chainType": "solana",
                "chainId": 103,
                "address": "2yAEzsC4GPCT3kGq39K5KLAqPFo4xzvNShDZHqCWo4Gx",
                "primary": true,
                "createdAt": "2022-06-20T16:39:41.138Z",
                "id": "04e421417221"
            },
            "user": {
                "id": "c4367732ab0c",
                "username": "ani",
                "addresses": [],
                "profile": {
                    "profilePictureKey": "B0XXqROJDwzTVm8LR1qHqVdJn3QD5grceudHLbV7cuVoWrdUnYPr8OwsnYgL2ch2"
                }
            }
        },
        {
            "address": {
                "chainType": "solana",
                "chainId": 103,
                "address": "2yAEzsC4GPCT3kGq39K5KLAqPFo4xzvNShDZHqCWo4Gx",
                "primary": true,
                "createdAt": "2022-06-20T16:39:41.138Z",
                "id": "04e421417221"
            },
            "user": {
                "id": "c4367732ab0c",
                "username": "ani",
                "addresses": [],
                "profile": {
                    "profilePictureKey": "B0XXqROJDwzTVm8LR1qHqVdJn3QD5grceudHLbV7cuVoWrdUnYPr8OwsnYgL2ch2"
                }
            }
        },
        {
            "address": {
                "chainType": "solana",
                "chainId": 103,
                "address": "AXkcPCWrWYGuayYgKp7y6LhugKzq5f3pqeKnrSod9ufy",
                "primary": true,
                "createdAt": "2022-08-17T20:24:26.627Z",
                "id": "1a6f2b51ad80"
            },
            "user": {
                "id": "da792fee8f1c",
                "username": "sabina",
                "addresses": [],
                "profile": {
                    "profilePictureKey": "AbWZwbpnaHBWBIs85cpF6zekYDGeD0SsiqHoEPwM2OTqeUZk9ydjvKM1JXeSIeJt"
                }
            }
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
