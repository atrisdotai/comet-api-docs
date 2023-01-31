---
description: Sign any message with your customers' Comet wallet.
---

# useSignMessage

Since Comet accounts come with a built-in cloud wallet, you can use this wallet to cryptographically sign messages on behalf of the user using the `useSignMessage` hook. The user will be prompted to log in if necessary, and will be asked to confirm the message to be signed (similar to the flow for Metamask or Phantom wallets).

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-01-31 at 11.55.59 AM.png" alt=""><figcaption></figcaption></figure>

## API

```javascript
const { signMessage } = useSignMessage({ message: '<MESSAGE>' });
```

`signMessage` is a function that can be called later on, which will bring up the confirmation dialog. It returns a successful `Promise` containing the signed message, or a failed `Promise` if the user clicks "Cancel".

## Example

{% code title="App.js" %}
```tsx
import { useSignMessage } from '@comet-labs/react';

function App() {
  const { signMessage } = useSignMessage({ message: 'gm world' });

  return (
    <div className="App">
      <button onClick={signMessage}>
        click here to sign message
      </button>
    </div>
  );
}
```
{% endcode %}
