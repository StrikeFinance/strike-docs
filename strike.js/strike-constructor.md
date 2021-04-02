# Strike Constructor

Creates an instance of the Strike.js SDK.

* `[provider]` \(Provider \| string\) Optional Ethereum network provider. Defaults to Ethers.js fallback mainnet provider.
* `[options]` \(object\) Optional provider options.
* `RETURN` \(object\) Returns an instance of the Strike.js SDK.

```text
var strike = new Strike(window.ethereum); // web browser

var strike = new Strike('http://127.0.0.1:8545'); // HTTP provider

var strike = new Strike(); // Uses Ethers.js fallback mainnet (for testing only)

var strike = new Strike('ropsten'); // Uses Ethers.js fallback (for testing only)

// Init with private key (server side)
var strike = new Strike('https://mainnet.infura.io/v3/_your_project_id_', {
  privateKey: '0x_your_private_key_', // preferably with environment variable
});

// Init with HD mnemonic (server side)
var strike = new Strike('mainnet' {
  mnemonic: 'clutch captain shoe...', // preferably with environment variable
});
```

