[Back](./README.md)
Cryptography is the branch of science concerned with keeping secrets secret.

* The message that is to be transmitted is called plaintext which will be referred to as "m". It may be in the form of text, digit, executable program or any other type. [[1]](https://ucalgary-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01UCALG_ALMA51645328230004336&context=L&vid=UCALGARY&lang=en_US&search_scope=ONLINE_ONLY&adaptor=Local%20Search%20Engine&isFrbr=true&tab=everything&query=any,contains,basic%20cryptography&offset=0)

* The key will be referred as "k"
* Ciphertext which is the result of the plaintext being encrypted will be referred as "c"

## Symmetric-Key Encryption
Symmetric encryption means that one key will be used for both encrypting and decrypting. Alice and Bob first agree on a key k. They both keep this key secret.
1. Alice encrypts message "m" by using an algorithm E as well as the key. This creates ciphertext "c". 
2. Bob uses decrypting algorithm D along with key k to obtain message "m".

A basic problem in a symmetric scheme is how Alice and Bob can agree on a shared secret key k in a secure and efficient way. 
There were no solutions to the key exchange problem until public-key cryptography was discovered 44 years ago by Martin Hellman, Ralph Merkle and Whitfield Diffie.

Some examples of symmetric-key encryption algorithms:
### Vernam's one-time pad
 Encryption is achieved by performing a bitwise XOR between m and k. Decryption is achieved by bitwise XOR between k and c.
 Four criteria that must be met for the encryption to work:
 1. The Key must be random
 2. The Key must be as long as the plaintext
 3. The Key must never be re-used in whole or in part
 4. The key must be kept completely secret  

Some of the disadvantages are seen from the requirements, mainly having to create a random key and that it must be the length of "m". 
The Vernam one-time pad ensures the confidentiality but fails to protect the message against modification.
### DES
 The DES algorithm takes 56-bit keys and 64-bit plaintext messages to output a 64-bit cryptogram. 
    
### AES
* Stands for Advanced Encryption Standard
* Developed by J.Daeman and V.Rijmen. 
* AES fixes block length to 128 bits, and uses three key lengths 128, 192 and 256 bits.

## Bibliography
1. Hans Delfs and Helmut Knebl. 2007. Introduction to Cryptography Principles and Applications. Second Edition. Berlin, Heidelberg: Springer.