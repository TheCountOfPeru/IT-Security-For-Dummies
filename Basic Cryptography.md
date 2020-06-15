#### [Back](./README.md)

## Cryptography

Cryptography is the branch of science concerned with keeping secrets secret. Cryptography provides secure communication in the presence of third parties trying to access it. 

* The message that is to be transmitted is called plaintext which will be referred to as "m". It may be in the form of text, digit, executable program or any other type. This is what we wish to protect from others accessing it. [[1]](https://ucalgary-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01UCALG_ALMA51645328230004336&context=L&vid=UCALGARY&lang=en_US&search_scope=ONLINE_ONLY&adaptor=Local%20Search%20Engine&isFrbr=true&tab=everything&query=any,contains,basic%20cryptography&offset=0)

* The key will be referred as "k". It will be used to encrypt the plaintext.
* Ciphertext which is the result of the plaintext being encrypted will be referred as "c"

## Symmetric-Key Encryption
Symmetric encryption means that one key will be used for both encrypting and decrypting. Alice and Bob first agree on a key k. They both keep this key secret.

1. Alice encrypts message "m" by using an algorithm E as well as the key. This creates ciphertext "c". 
2. Bob uses decrypting algorithm D along with key k to obtain message "m".

There are two notions to go about encrypting the plaintext in symmetric-key encryption. One is the notion of **stream cipher** which processes the plaintext bit by bit. The other is **block cipher** which converts plaintext into ciphertext by splitting the plaintext into blocks first, the size of the block could vary by algorithm, the DES algorithm splits it into 8 bytes (64 bits).

A basic problem in a symmetric scheme is how Alice and Bob can agree on a shared secret key k in a secure and efficient way. 
There were no solutions to the key exchange problem until public-key cryptography was discovered 44 years ago by Martin Hellman, Ralph Merkle and Whitfield Diffie.

Some examples of symmetric-key encryption algorithms are:
* Vernam's one-time pad
* DES
* AES

### Vernam's one-time pad
 This is the most famous example of a stream cipher. Encryption is achieved by performing a bitwise exclusive or (XOR) between m and k. Decryption is achieved by bitwise XOR between k and c.
 Four criteria that must be met for the encryption to work:
 1. The Key must be random
 2. The Key must be as long as the plaintext
 3. The Key must never be re-used in whole or in part
 4. The key must be kept completely secret  

Some of the disadvantages are seen from the requirements, mainly having to create a random key and that it must be the length of "m". 
The Vernam one-time pad ensures the confidentiality but fails to protect the message against modification.
### DES
A block cipher that stands for **Data Encryption Standard** which was proposed by IBM back in 1974.

* The DES algorithm takes 56-bit keys. The keys are apparently each 64 bits long **but** every 8th key bit is ignored in the DES algorithm. Thus effectively "k" is 56 bits 
* It takes 64-bit plaintext messages
* It outputs a 64-bit cryptogram. 

**An Overview of how DES works**

The encryption with DES starts by taking the key and permutating the bits of the key. In the image below, what was the 58th bit becomes the first bit, the 50th bit becomes the second and so on.
![DES Initial Permutation](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/Initial-Permutation.png)

![DES IP](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/Initial-Permutation.png)

[Source](https://en.wikipedia.org/wiki/DES_supplementary_material)

This permutation is then split into half. A left shift for both pieces is then performed and then the split pieces are placed back together in a special way. This is how we get our first subkey. It is important to note that of the 64 bits we started with, the subkey will contain 48 bits. DES consists of **16** steps, called rounds.

The main disadvantage of DES is that it can be broken using brute-force search. However, 3DES, which applies the DES algorithm 3 times is considered secure. 
    
### AES
* Stands for Advanced Encryption Standard
* Developed by J.Daeman and V.Rijmen. 
* AES fixes block length to 128 bits, and uses three key lengths 128, 192 and 256 bits.

## What is Asymmetric cryptography ?
It is a type of cryptography that uses keys. All users get two keys:

* One public key
* One private key

Users exchange their public keys to communicate with each other. Any user can encrypt a message as long as they have the receiver's public key. The message however, can only be decrypted by the receiver's private key. The blockchain uses asymmetric cryptography to achieve two goals:

* Identifying accounts (public keys)
* Authorizing transactions

In Symmetric cryptography, only one key is used to both encrypt and decrypt.

## Bibliography
[[1.]](https://ucalgary-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01UCALG_ALMA51645328230004336&context=L&vid=UCALGARY&lang=en_US&search_scope=ONLINE_ONLY&adaptor=Local%20Search%20Engine&isFrbr=true&tab=everything&query=any,contains,basic%20cryptography&offset=0)Hans Delfs and Helmut Knebl. 2007. Introduction to Cryptography Principles and Applications. Second Edition. Berlin, Heidelberg: Springer.
