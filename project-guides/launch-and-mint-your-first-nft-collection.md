# Launch and mint your first NFT collection

_Time: 15-30min_

The Comet SDK lets you launch new Solana NFT collections, and lets anyone mint them using a credit card. Never worry about a wallet private key or clunky fiat onramp again.

## First things first

You’ll need your **Comet API key** and **Comet publishable key**. For instructions, go to the link below:

{% content-ref url="../getting-started.md" %}
[getting-started.md](../getting-started.md)
{% endcontent-ref %}

In addition, if you want to launch a paid NFT collection, you need to set up Stripe x Comet to send payments to your bank account. To do this, go to [withcomet.com/settings/payments](http://withcomet.com/settings/payments) and log in using the **same phone number** you used to create your API key.

## Launching a new collection

To launch a new collection, you’ll need one thing - an image. Preferably 840x840, which will be part of the membership pass. Once you have that file on your computer, you’re ready to get started.

{% hint style="success" %}
The examples in this doc will use `cURL` to call the Comet REST API, but you can do this via Javascript, Python, or any other language you’d like!
{% endhint %}

To launch a collection using the Comet REST API, you’ll need the following information:

1. Your Comet API key (see **First things first** above)
2. The name and symbol you want for your NFT
3. The description of the membership pass
4. The price you want to sell your pass for (in USD)
5. The maximum supply of the token
6. The path to the image on your computer

Once you have those ingredients, you can call the REST API as follows:

```bash
curl -X POST 'https://api.withcomet.com/v1/collection' \
     -H "Authorization: Bearer <COMET API KEY>" \
     -F name='my test collection' \
     -F symbol='TEST' \
     -F description='whats good' \
     -F price=10 \
     -F maxSupply=100 \
     -F backgroundUpload=@/path/to/image.jpg
```

You’ll get a result that looks like this:

```json
{
  "id": "f4b2e771029e",
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
  "backgroundUpload": "VYkbVHtWhV3LakmWYhOVMMURs24Adk9yH1Bp6G1W4dklE1fZIfaMuJqdvSkzKOwl"
}
```

Congrats! You’ve started to deploy your first NFT collection with Comet. You can use the `id` to retrieve this collection from the API later on:

```bash
curl -X GET 'https://api.withcomet.com/v1/collection/<ID>' \
     -H "Authorization: Bearer <COMET API KEY>"
```

Once `deployed` is equal to `true`, you’re officially live on Solana mainnet! Usually deployment takes 30-60 seconds.

## Letting others mint your collection

Comet provides a React component you can drop in to any project, which lets any user mint your NFT (including accepting credit card if the NFT requires it). To get started, create a new [Create React App](https://create-react-app.dev/docs/getting-started/) project (instructions are in the link). Once you’ve created it, just do the following:

First, install the Comet React SDK (v1 alpha) in your project:

```bash
npm install --save @comet-labs/react@alpha
```

In your `index.js`, you will need to wrap your entire app in a `CometProvider`. The `CometProvider` component unlocks Comet's Web3 functionality for the rest of your app's components. You will need to provide your **Comet publishable key** here.

{% code title="index.js" %}
```tsx
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

Then, in your `App.js`, you can simply import the `MintButton` component and drop it into the page. Here you will need the `collectionId` from the collection you created earlier in the tutorial.

{% code title="App.js" %}
```jsx
import logo from './logo.svg';
import './App.css';
import { MintButton } from '@comet-labs/react';

function App() {
  return (
    <div className="App">
      <MintButton
        collectionId="<ID>"
      />
    </div>
  );
}

export default App;
```
{% endcode %}

Run `npm run start` and you’ll see a mint button. Now mint your NFT with a credit card without ever touching a crypto wallet!

<figure><img src="../.gitbook/assets/Screen Shot 2023-01-10 at 12.40.13 PM.png" alt=""><figcaption></figcaption></figure>
