# Bitgesell Blockchain documentation
A comprehensive documentation for Bitgesell Bockchain SDK updated on each major release.

## Getting started with the SDK

Install via yarn/npm:
```sh
yarn add bitgesell-blockchain-sdk # npm i bitgesell-blockchain-sdk 
```

### Initialization

To initialize the sdk library

```javascript
import {BitgesellBlockchainSDK} from 'bitgesell-blockchain-sdk'

const sdkConfig = {
  baseAPIURL: 'https://api.bitaps.com/bgl/v1/blockchain',
 logger: console.log // optional
}

const bitgesellBlockchainSDK = new BitgesellBlockchainSDK(sdkConfig)
```

To initialize the sdk library in Commonjs pattern:

```javascript
const {BitgesellBlockchainSDK} = require('bitgesell-blockchain-sdk')

const sdkConfig = {
  baseAPIURL: 'https://api.bitaps.com/bgl/v1/blockchain',
 logger: console.log // optional
}

const bitgesellBlockchainSDK = new BitgesellBlockchainSDK(sdkConfig)
```
## A few examples

### Query Transactions
To query transacton by the transaction `hash`:

```javascript
(async() => {
    const txHash = 'e56d609044b4839d840ef4db4ac0534306cc11b257b8b4a71e8fb7491aaca9a9'
    const transaction = await bitgesellBlockchainSDK.tx.getTransactionByHash(txHash)
    console.log(transaction)
})()
```
### Query the Mempool
To query mempool state:

```javascript
(async() => {
    const mempoolState = await bitgesellBlockchainSDK.mempool.getMempoolState()
    console.log(mempoolState)
})()
```

## License
`MIT`