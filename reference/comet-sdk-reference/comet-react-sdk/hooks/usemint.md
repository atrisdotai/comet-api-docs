---
description: Start the process of minting a token.
---

# useMint

If you want a custom minting experience without using the pre-existing `MintButton` component, you can also initiate the mint process for a customer with the `useMint` hook. This hook will open a payment modal (if necessary) and start minting a token to the user.

## API

```jsx
const { startMint } = useMint({ collectionId: "<COLLECTION ID>" });
```

Much like the [`MintButton` component](../components.md#mintbutton), you can supply `collectionId` to the `useMint` hook. If the user is not logged in, login will first be prompted.

## Example

```jsx
import { useMint } from '@comet-labs/react';

function App() {
  const { startMint } = useMint({ collectionId: 'ac37722abd3b' });

  return (
    <div className="App">
      <button onClick={startMint}>
        Custom mint button
      </button>
    </div>
  );
}
```
