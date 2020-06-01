# Blockchain

## What is it?
"A public, permanent, append-only distributed ledger."[[1]](https://www.technologyreview.com/2018/04/23/143477/explainer-what-is-a-blockchain/). The [Blockchain](https://en.wikipedia.org/wiki/Blockchain) is like a record, or spreadsheet containing information about transactions. It is a series of linked data blocks, nothing can be erased from it but new blocks can be added.

## Why should I care?

There is a huge potential for cost cutting by getting rid of middlemen in different industries. This would lead to lower prices for us as consumers.
* Blockchain has the potential to disrupt traditional financial institutions. Transaction fees to transfer money between countries would be much lower.
* It could be used as the backbone for a new voting system
* It is a perfect tool for keeping records of ownership.
* Blockchain could be used to achieve and maintain integrity in peer to peer (P2P) systems. 

## Is it secure?
Immutability is theoretically possible, this is due to the decentralization nature of blockchain which would require one to take control  of more than 51% of computers in the same distributed ledger and be able to alter records within a very short time. This is about 10 minutes for a platform like Bitcoin. This has yet to happen as of this writing. [[2]](https://blogs.adb.org/blog/how-secure-blockchain)
![Centralized vs Decentralized](https://www.bitdegree.org/tutorials/wp-content/uploads/2018/06/centralized-vs-decentralized-1-1.jpg)
* The bigger the network, the more tamper-resistant it becomes. 

### Immutability
Three elements to make the history of blockchain transactions data immutable:[[4]](https://learning.oreilly.com/library/view/blockchain-basics-a/9781484226049/A436689_1_En_16_Chapter.html)
* Storing the data such that the slightest manipulation becomes noticeable and stands out.
* Making the tampering of data computationally expensive
* Enforcing to rewrite the history for changes. 

## Security in the Blockchain
**Hash Functions** and **Asymmetric cryptography** are technologies used extensively in the Blockchain.

## What are Hash Functions?
A function that maps an arbitrary size of data to a fixed-sized value. It is usually used so that passwords or keys are hashed and this hash value is stored rather than the password or key itself.

The Blockchain is concerned with cryptographic hash functions which have the following properties[[3]](https://www.amazon.com/Blockchain-Basics-Non-Technical-Introduction-Steps/dp/1484226038):
* Provide hash values for any kind of data quick
* Deterministic
    * Meaning the hash function will yield identical hashes for identical data.
* Pseudorandom
    * Meaning that even if the input data were changed only a little bit, the resulting hash values will differ unpredictably.The objective is to deter others from predicting the hash value based on the input data.
* One-way function
    * Do not provide any way to trace its input values by its output.
* Collision resistant 
    * meaning the chances of identical hash values for different data are small.
    
## What is Asymmetric cryptography  ?
It is a type of cryptography that uses keys. All users get two keys:
* One public key
* One private key 

Users exchange their public keys to communicate with each other. Any user can encrypt a message as long as they have the receiver's public key. The message however, can only be decrypted by the receiver's private key.
The blockchain uses asymmetric cryptography to achieve two goals:
* Identifying accounts (public keys)
* Authorizing transactions

In Symmetric cryptography, only one key is used to both encrypt and decrypt.

## Validation Rules to add Blocks
The activity of adding a new block to the blockchain is called mining.
1. Block must contain a valid hash reference to a previous block.
2. Block must contain a valid root of a Merkle tree containing transaction data
3. Block must contain a correct difficulty level
4. Block's new time stamp is after the time stamp of its preceding block header
5. Block must contain nonce. 
    * "A nonce is an arbitrary number that can be used just once in a cryptographic communication." [[5]](https://en.wikipedia.org/wiki/Cryptographic_nonce) 
6. The hash value of all the five pieces of data combined together fulfills the difficulty level. 