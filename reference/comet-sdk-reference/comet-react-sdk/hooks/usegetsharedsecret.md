---
description: >-
  Generate a shared secret using Elliptic Curve Diffie-Hellman key exchange with
  your customers' Comet wallet.
---

# useGetSharedSecret

{% hint style="info" %}
`useGetSharedSecret` is an advanced feature of Comet's React SDK. Except for situations which require secure symmetric encryption, you will probably not need this React hook.
{% endhint %}

Using Comet's built in cloud wallets, users can perform Diffie-Hellman key exchange to generate a shared secret with another party's Solana public key. This shared secret can be used for secure communication between two Solana addresses.

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-01-31 at 12.33.38 PM.png" alt=""><figcaption></figcaption></figure>

## API

```javascript
const { getSharedSecret } = useGetSharedSecret({ publicKey: '<SOLANA ADDRESS>' });
```

In the example above, the `publicKey` can be a `string`, `Buffer`, or `Uint8Array`.

`getSharedSecret` is a function that can be called later on, which will bring up the confirmation dialog. Users will be prompted to log in to Comet if needed. When the user clicks "Confirm", a shared secret will be calculated between the user's private key and the supplied public key.

`getSharedSecret` returns a successful `Promise` containing the shared secret in `Uint8Array` format if the user clicks "Confirm"; otherwise it will return a failed `Promise` if the user clicks "Cancel".

## Example

```tsx
import { useGetSharedSecret } from '@comet-labs/react';

function App() {
  const { getSharedSecret } = useGetSharedSecret({ publicKey: 'Dgq5B8i5NJJfPoUgpkFZDzRr84zd1BJrUBntJt1EBvgd' });

  return (
    <div className="App">
      <button onClick={getSharedSecret}>
        click for diffie hellman
      </button>
    </div>
  );
}
```
