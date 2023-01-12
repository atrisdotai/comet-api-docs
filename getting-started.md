# Getting Started

To get started using the Comet SDK, you'll need to get a Comet API key. To get one, run the following command in a terminal (replacing `<NUMBER>` with your phone number):

```bash
curl -X POST 'https://api.withcomet.com/comet/auth/phone/send' \
     -H 'content-type: application/json' \
     -d '{"number": "<NUMBER>", "developer": true}'
```

You'll receive an SMS message with a 6-digit code. Once you get it, feed this code into the terminal as follows:

```bash
curl -X POST 'https://api.withcomet.com/comet/auth/phone/verify' \
     -H 'content-type: application/json' \
     -d '{"number": "<NUMBER>", "code": "<CODE>"}'
```

You'll get a JSON that looks like the following:

```json
{
  "token": {
    "string": "Qa5rusKnfGvIvfgV37K3VE98a6V57JM6",
    "valid": true,
    "developer": true,
    "createdAt": "2023-01-12T04:50:29.800Z",
    "expires": null
  },
  "redirect": "/"
}
```

The value in `token.string` is your Comet developer API key. Keep it safe, and use it to call your API endpoints in the Comet REST API.
