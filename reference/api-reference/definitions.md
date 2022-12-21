# Definitions

## Getting all definitions

{% swagger method="get" path="/definitions" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets all definitions" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful operation" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Getting a definition by id

{% swagger method="get" path="/definitions" baseUrl="https://api.withcomet.com/rest/v1" summary="Gets a definition by id" %}
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

## Creating a definition

{% swagger method="post" path="/definitions" baseUrl="https://api.withcomet.com/rest/v1" summary="Creates a new definition" %}
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
