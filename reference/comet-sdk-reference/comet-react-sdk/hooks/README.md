---
description: React hooks allow for more customizable Web3 experiences with the Comet SDK.
---

# Hooks

{% hint style="info" %}
Comet React hooks will not work unless they are used in components wrapped with a `CometProvider`. See the [`CometProvider` page](../components.md#cometprovider) for details.
{% endhint %}

### Getting the logged-in account

Use the `useAccount` hook to grab the current user's information, including username and Solana address.

{% content-ref url="useaccount.md" %}
[useaccount.md](useaccount.md)
{% endcontent-ref %}

### Starting the mint process

Use the `useMint` hook to bring up the mint dialog for your customers, where they can confirm the transaction and pay via credit card if needed.

{% content-ref url="usemint.md" %}
[usemint.md](usemint.md)
{% endcontent-ref %}

### Signing arbitrary messages

Use the `useSignMessage` hook to sign any message using the customer's Comet wallet.

{% content-ref url="usesignmessage.md" %}
[usesignmessage.md](usesignmessage.md)
{% endcontent-ref %}

### Signing Solana transactions

Use the `useSignTransaction` hook to partially sign a Solana Web3 transaction using the customer's Comet wallet. The customer will be asked to confirm signing.

{% content-ref url="usesigntransaction.md" %}
[usesigntransaction.md](usesigntransaction.md)
{% endcontent-ref %}

### \[Advanced] Diffie-Hellman key exchange

Use the `useGetSharedSecret` hook to perform ECDH with the customer's private key and another public key.

{% content-ref url="usegetsharedsecret.md" %}
[usegetsharedsecret.md](usegetsharedsecret.md)
{% endcontent-ref %}
