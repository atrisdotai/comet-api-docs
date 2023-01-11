# Collection

## Get Collection Owners

{% swagger method="get" path="/collection/:collectionId/owners" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets a collection's owners." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="path" name="collectionId" %}
id of collection
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    "owners": [
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

## Get Created Collections (TODO)

{% swagger method="get" path="/definitions" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets collections created by you." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" %}
The definition id
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    // Response
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

## Create Collection (TODO)

{% swagger method="post" path="/collection" baseUrl="https://api.withcomet.com/rest/v1" summary="Creates a new collection." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" required="true" type="String" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="String" required="true" %}
The name of the collection
{% endswagger-parameter %}

{% swagger-parameter in="body" name="symbol" type="String" required="true" %}
The symbol of the collection
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" required="true" %}
The description of the collection
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="String" required="true" %}
The type of the collection

\


(ethereum: erc20, erc721

\


solana: spl, metaplex_candy_machine_nft, milky_way_nft)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chainType" type="String" required="true" %}
The type of the chain

(evm or solana)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chainId" type="String" required="true" %}
The chain id

(ethereum: 137, 80001\
solana: 101, 103)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="subType" type="String" %}
The sub type of the collection, only for solana

\


(numbered_pass or static_pass)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="config" type="Json" %}
The config of the deployment
{% endswagger-parameter %}

{% swagger-parameter in="body" name="communityId" type="Strin" required="true" %}
The community id, only for solana
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Invalid payload" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Community does not exist" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
