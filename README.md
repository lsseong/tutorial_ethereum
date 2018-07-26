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


### Create an account and the keystore file
https://medium.com/@julien.maffre/what-is-an-ethereum-keystore-file-86c8c5917b97

### Wallet - a smart contract, DApp

dApp is a blockchain enabled website or portal, and smart contract connects dApp with blockchain

With official Ethereum Wallet (EW) you are running a full node, downloading blockchain and syncing it. With myetherwallet (MEW) there is no such need, it's just a wallet and interface to the blockchain.

Mist is: EW + web browser + dApp interface

Parity is an alternative well-respected user friendly wallet: https://parity.io/

https://github.com/ethereum/meteor-dapp-wallet
https://ethereum.stackexchange.com/questions/212/whats-the-difference-between-accounts-and-wallets-in-mist
https://www.quora.com/What-is-the-difference-between-smart-contracts-and-dapps

MIST - https://ethereum.stackexchange.com/questions/2690/what-is-the-relationship-between-mist-and-ethereum-wallet

### Transaction Lifecycle
https://medium.com/blockchannel/life-cycle-of-an-ethereum-transaction-e5c66bae0f6e

### Recursive Length Prefix (RLP) Encoding/Decoding
https://medium.com/coinmonks/data-structure-in-ethereum-episode-1-recursive-length-prefix-rlp-encoding-decoding-d1016832f919

### Trie

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

### The Yellow Paper
https://ethereum.github.io/yellowpaper/paper.pdf

### Security
https://www.ledger.fr/2016/08/08/how-to-properly-secure-cryptocurrencies-exchanges/


