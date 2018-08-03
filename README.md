# tutorial_ethereum

### The wiki
https://github.com/ethereum/wiki/wiki

### Geth and MIST
Geth (Go Ethereum) is an implementation of an Ethereum node in the Go programming language. It has a command line interface.
Mist is a (UI) program which connects to Geth in the background, and also serves as an interface for the wallet. You do not need to run Geth. Mist will run it for you invisibly.

MIST has two versions for download [https://github.com/ethereum/mist/releases]
Mist-installer = a web for Ethereum browser, a wallet interface
Ethereum-Wallet = a wallet interface (browser functionality removed for safety)

https://bitfalls.com/2018/02/12/explaining-ethereum-tools-geth-mist/

Parity is another implementation of an Ethereum node: https://parity.io/

### Create an account and the keystore file
https://medium.com/@julien.maffre/what-is-an-ethereum-keystore-file-86c8c5917b97

### Wallet - a smart contract, DApp

dApp is a blockchain enabled website or portal, and smart contract connects dApp with blockchain

With official Ethereum Wallet (EW) you are running a full node, downloading blockchain and syncing it. With myetherwallet (MEW) there is no such need, it's just a wallet and interface to the blockchain.

https://github.com/ethereum/meteor-dapp-wallet
https://ethereum.stackexchange.com/questions/212/whats-the-difference-between-accounts-and-wallets-in-mist
https://www.quora.com/What-is-the-difference-between-smart-contracts-and-dapps

These wallets have been verified to support Ethereum ERC20 tokens:

 - MyEtherWallet (MEW, Online and local browser) - https://www.myetherwallet.com/. Use Node.js crypto module to generate keys on local machine. The online part is for sending transaction to ethereum nodes through their public infrastructure using secured TLS.
 - MetaMask (Firefox and Chrome browser extension) - https://metamask.io/. Stores private keys in the browser local data store.
 - MIST (Desktop) - https://ethereum.stackexchange.com/questions/2690/what-is-the-relationship-between-mist-and-ethereum-wallet
 - Parity (Desktop) 
 - Jaxx (iPhone and Android)

More here https://tokenmarket.net/what-is/how-to-participate-ethereum-token-crowdsale/


### Transaction Lifecycle
https://medium.com/blockchannel/life-cycle-of-an-ethereum-transaction-e5c66bae0f6e

### Recursive Length Prefix (RLP) Encoding/Decoding
https://medium.com/coinmonks/data-structure-in-ethereum-episode-1-recursive-length-prefix-rlp-encoding-decoding-d1016832f919

### Trie - data structure to hold transaction and hashing

Radix - a tree structure to lookup value by path
Patricia - a radix tree with 2 child nodes
Merkle - a tree structure where node value is a hash of child nodes
Patricia - a mixture of radix and merkle tries (used in Etherium)

Radix and Patricia Tries - https://cs.stackexchange.com/questions/63048/what-is-the-difference-between-radix-trees-and-patricia-tries/63060#63060

Merkle-Patricia-trie - https://ethereum.stackexchange.com/questions/6415/eli5-how-does-a-merkle-patricia-trie-tree-work

Radix-Merkle trie - https://medium.com/coinmonks/data-structure-in-ethereum-episode-2-radix-trie-and-merkle-trie-d941d0bfd69a

Modified Merkle Patricia Trie (used by Ethereum) 
- https://github.com/ethereum/wiki/wiki/Patricia-Tree
- https://easythereentropy.wordpress.com/2014/06/04/understanding-the-ethereum-trie/
- https://medium.com/coinmonks/data-structure-in-ethereum-episode-3-patricia-trie-b7b0ccddd32f

### A block architecture using Merkle Patricia Trie

https://ethereum.stackexchange.com/questions/268/ethereum-block-architecture/6413#6413

### Solidy - the programming language to code smart contract
https://solidity.readthedocs.io/en/latest/introduction-to-smart-contracts.html
IDE: https://truffleframework.com/


### The Yellow Paper
https://ethereum.github.io/yellowpaper/paper.pdf

### Security
https://www.ledger.fr/2016/08/08/how-to-properly-secure-cryptocurrencies-exchanges/

### msg.value and this.balance
- msg.value is the amount of ETH sent to a payable public method in a contract.
- this.balance is the amount of ETH stored in the contract.

The value of this.balance in payable methods is increased by msg.value before the body of your payable method executes. If your contract has a starting balance of 1 and you pass in a msg.value of 2, the payable method will already have a this.balance of 3 when it executes.

### Events, logs and transaction receipts
Events, logs, and event logs are usually Ethereum terms that are interchangeable (in some contexts a particular term is favored, for example events in Solidity and web3.js, and logs as in the EVM and Yellow Paper).

Events/logs are the result of LOG opcodes being executed in the EVM. They are a part of "internal transactions" which are derived by executing transaction data through the EVM.

Logs are stored as an array in a transaction receipt that has the following data structure:

```
blockHash: String, 32 Bytes - hash of the block where this transaction was in.
blockNumber: Number - block number where this transaction was in.
transactionHash: String, 32 Bytes - hash of the transaction.
transactionIndex: Number - integer of the transactions index position in the block.
from: String, 20 Bytes - address of the sender.
to: String, 20 Bytes - address of the receiver. null when its a contract creation transaction.
cumulativeGasUsed: Number - The total amount of gas used when this transaction was executed in the block.
gasUsed: Number - The amount of gas used by this specific transaction alone.
contractAddress: String - 20 Bytes - The contract address created, if the transaction was a contract creation, otherwise null.
logs: Array - Array of log objects, which this transaction generated.
```

### Events and logs listener
https://media.consensys.net/technical-introduction-to-events-and-logs-in-ethereum-a074d65dd61e

### Escrow contract
https://medium.com/@s_van_laar/how-to-build-an-escrow-contract-with-an-ethereum-erc20-token-bfc4825b0dd7
