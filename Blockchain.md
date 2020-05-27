# Blockchain

## What is it?
"A public, permanent, append-only distributed ledger."[[1]](https://www.technologyreview.com/2018/04/23/143477/explainer-what-is-a-blockchain/). The [Blockchain](https://en.wikipedia.org/wiki/Blockchain) is like a record, a ledger or spreadsheet containing information about transactions. It is a series of linked data blocks, nothing can be erased from it but new blocks can be added.

## Why should I care?
* Blockchain has the potential to disrupt traditional financial institutions.
* It could be used as the backbone for a new voting system
* It is a perfect tool for keeping records of ownership.

## Is it secure?
Immutability is theoretically possible, however, the decentralization nature of blockchain would require one to take control  of more than 51% of computers in the same distributed ledger and be able to alter records within a very short time. This is about 10 minutes for a platform like Bitcoin. This has yet to happen as of this writing. [[2]](https://blogs.adb.org/blog/how-secure-blockchain)
![Centralized vs Decentralized](https://www.bitdegree.org/tutorials/wp-content/uploads/2018/06/centralized-vs-decentralized-1-1.jpg)
* The bigger the network, the more tamper-resistant it becomes. 

## Security Concepts in Blockchain
Hash Functions and Asymmetric cryptography are technologies used extensively in Blockchain.

## What are Hash Functions?
A function that maps an arbitrary size of data to a fixed-sized value. It is usually used so that passwords or keys are hashed and this hash value is stored rather than the password or key itself.
## What is Asymmetric cryptography  ?
It is a type of cryptography that uses keys. All users get two keys:
* One public key
* One private key 

Users exchange their public keys to communicate with each other. Any user can encrypt a message as long as they have the receiver's public key. The message however, can only be decrypted by the receiver's private key.

In Symmetric cryptography, only one key is used to both encrypt and decrypt.