---
description: Get the current logged-in user's account.
---

# useAccount

You can use Comet's login system across your entire app with the `useAccount` hook. This hook will tell you if a user is logged in to Comet or not. If they are logged in, it will return that user's account information.

## API

```jsx
const account = useAccount();
```

The `account` object contains the following fields:

* `id` - the Comet User ID of the logged-in user.
* `username` - the username of the logged-in user.
* `address` - the Solana address of the logged-in user.

If no user is logged in, `account` will be null.

## Example

{% code title="App.js" %}
```jsx
import { LoginButton, useAccount } from '@comet-labs/react';

function App() {
  const account = useAccount();
  
  return (
    <div className="App">
      <LoginButton />
      <br />
      {
        account && `Successfully logged in! Welcome, @${account.username}!`
      }
    </div>
  );
}
```
{% endcode %}
