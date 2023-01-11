---
description: A suite of API endpoints that simplify the Solana NFT ecosystem.
---

# Comet REST API

With Comet's REST API, you can launch new NFT collections, distribute them quickly to your users, and see who owns what. Never worry about RPC nodes again – just get a Comet developer API key and start hacking!

{% hint style="info" %}
Comet is currently on version 1 of the REST API. The base URL for all requests is `https://api.withcomet.com/v1/`.
{% endhint %}

### Collections

With the `/collection` endpoints, you can query existing NFT collections or launch new ones.

{% content-ref url="collections.md" %}
[collections.md](collections.md)
{% endcontent-ref %}

### Airdrops

Once you've launched a new collection, start giving it out to your users! The `/airdrop` endpoints give fine-grained control over who receives which tokens.

{% content-ref url="airdrops.md" %}
[airdrops.md](airdrops.md)
{% endcontent-ref %}

### Gallery

With the `/gallery` endpoint, you can see which tokens any address or Comet user owns.

{% content-ref url="gallery.md" %}
[gallery.md](gallery.md)
{% endcontent-ref %}

### Usage

Quickly view your API usage with the `/usage` endpoint.

{% content-ref url="usage.md" %}
[usage.md](usage.md)
{% endcontent-ref %}
