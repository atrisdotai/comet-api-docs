---
description: React components you can drop into your web app with 1 line of code.
---

# Components

## CometProvider

In order for the other components and hooks to work properly within your React application, you need to wrap your component tree with the `CometProvider` component. Doing so is simple; all you'll need is your Comet Publishable Key, obtainable at [www.withcomet.com/devstart](https://www.withcomet.com/devstart).

**It is important that you add `CometProvider` to your app, otherwise other components and hooks will not work properly!**

### API

| Prop             | Type    | Description                                                                                                              |
| ---------------- | ------- | ------------------------------------------------------------------------------------------------------------------------ |
| `publishableKey` | string  | **Required.** Your Comet Publishable Key.                                                                                |
| `showFullWallet` | boolean | If `true` (default), users will see a full Comet wallet + gallery when they log in. Otherwise, they'll see a minimal UI. |

### Example

{% code title="index.jsx" %}
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import './index.css';

import { CometProvider } from '@comet-labs/react';

const cometProviderConfig = {
  publishableKey: '<PUBLISHABLE KEY>',
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <CometProvider config={cometProviderConfig}>
      <App />
    </CometProvider>
  </React.StrictMode>
);
```
{% endcode %}

## LoginButton

A button that lets a user log in or sign up to Comet. When logged in, it shows the user's username and profile picture.

### API

No props are required for `LoginButton`.

### Example

{% code title="App.jsx" %}
```jsx
import { LoginButton } from '@comet-labs/react';

function App() {
  return (
    <div className="App">
      <LoginButton />
    </div>
  );
}
```
{% endcode %}

<div>

<figure><img src="../../../.gitbook/assets/Screenshot 2023-01-26 at 1.15.59 AM.png" alt=""><figcaption><p>The LoginButton when the user is not logged in.</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Screenshot 2023-01-26 at 1.28.11 AM.png" alt=""><figcaption><p>When a user logs in, they'll be able to see their Comet account and the gallery of NFTs in their wallet. This will be shown if <code>showFullWallet</code> is set to <code>true</code> in the <code>CometProvider</code> component.</p></figcaption></figure>

</div>

## MintButton

A drop-in button that lets users mint an NFT that's been launched with Comet.

### API

| Prop           | Type   | Description                                                                             |
| -------------- | ------ | --------------------------------------------------------------------------------------- |
| `collectionId` | string | **Required.** The ID of the Comet collection that can be minted with this `MintButton`. |

### Example

{% code title="App.jsx" %}
```jsx
import { MintButton } from '@comet-labs/react';

function App() {
  return (
    <div className="App">
      <MintButton collectionId="<COLLECTION ID>" />
    </div>
  );
}
```
{% endcode %}

<div>

<figure><img src="../../../.gitbook/assets/Screenshot 2023-01-26 at 1.26.28 AM.png" alt=""><figcaption><p>The <code>MintButton</code> displays the price and items remaining in the collection.</p></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Screenshot 2023-01-26 at 1.25.56 AM.png" alt=""><figcaption><p>If the collection requires payment, clicking the <code>MintButton</code> will redirect the user to a credit card payment form.</p></figcaption></figure>

</div>
