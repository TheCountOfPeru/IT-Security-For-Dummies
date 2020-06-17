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
There were no solutions to the key exchange problem until public-key cryptography was discovered 44 years ago (1976) by Martin Hellman, Ralph Merkle and Whitfield Diffie.

Some examples of symmetric-key encryption algorithms are:
* Vernam's one-time pad
* DES
* AES

## Vernam's one-time pad
 This is the most famous example of a stream cipher. Encryption is achieved by performing a bitwise exclusive or (XOR) between m and k. Decryption is achieved by bitwise XOR between k and c.
 Four criteria that must be met for the encryption to work:
 1. The Key must be random
 2. The Key must be as long as the plaintext
 3. The Key must never be re-used in whole or in part
 4. The key must be kept completely secret  

Some of the disadvantages are seen from the requirements, mainly having to create a random key and that it must be the length of "m". 
The Vernam one-time pad ensures the confidentiality but fails to protect the message against modification.

## DES
A block cipher that stands for **Data Encryption Standard** which was proposed by International Business Machines Corporation (IBM) back in 1974.

* The DES algorithm takes 56-bit keys. The keys are apparently each 64 bits long **but** every 8th key bit is ignored in the DES algorithm. Thus effectively "k" is 56 bits 
* It takes 64-bit plaintext messages
* It outputs a 64-bit cryptogram. 



**A simplified overview of how DES works**

The encryption with DES starts by taking the key and permutating the bits of the key. 

![DES Structure](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/des_structure.jpg)

[Source](https://www.tutorialspoint.com/cryptography/data_encryption_standard.htm)

This permutation is then split into half. A left shift for both halves is then performed and then the split pieces are placed back together in a special way. This is how we get our first **subkey**. It is important to note that of the 64 bits we started with, the subkey will contain 48 bits. DES consists of **16** steps, called rounds, therefore 16 subkeys will be made.

1. The plaintext (64 bits) is permutated using the Initial Permutation (IP). In the image below, what was the 58th bit becomes the first bit, the 50th bit becomes the second and so on.

![DES IP](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/Initial-Permutation.png)

[Source](https://en.wikipedia.org/wiki/DES_supplementary_material)

2. The permutated plaintext is split into two blocks, l<sub>0</sub> and r<sub>0</sub>.

3. The right half, r<sub>0</sub> , is padded so that we go from a 32 bit stream to a 48 bit stream. 

4. Perform XOR with Subkey 1 since now, both key and right side of plain-text are 48 bits.

5. The result from step 4 is now implemented into the Substitution boxes "S-boxes", which there are eight of for DES. 
    * They take 6 bits at a time of the 48 bits, where the outer bits of the 6 bits are used for the row while the 4 inner bits are used for the column. 

![S-box 5](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/FifthS-Box.png)

[Source](https://en.wikipedia.org/wiki/DES_supplementary_material)

Substitution box 5 of the 8. (Picture above)

6. The S-Box gives us a new 4 bit output (a number from 0 to 15 in decimal). This makes our right half 32 bits again from the 48 bits we had.

7. We then perform another permutation. Which re-arranges the positions of the bits.

8. Recall that we are manipulating the right side, r<sub>0</sub>. This right side that went through the Substitution box now gets XORed with the left side, l<sub>0</sub>. 
    * The result becomes our new right side for the second round, r<sub>1</sub>.
9. The original right side, r<sub>0</sub> , becomes our new left side, l<sub>1</sub>. 
10. This process must be repeated another 15 times for a total of 16 times.
11. A Final Permutation (FP) is performed on the combined block which produces the 64-bit ciphertext.

The main disadvantage of DES is that it can be broken using brute-force search. However, 3DES, which applies the DES algorithm 3 times is considered secure. The receiver would have the ciphertext and the key, which would allow him to get the plaintext.
    
### AES
Stands for Advanced Encryption Standard. It is another common block cipher. It was developed by two Belgian cryptographers; Vincent Rijmen and Joan Daeman. Some pointers:
* It takes a plaintext in 128 bits
* It outputs the ciphertext into 128 bits. 
* The key, however, can be of three key lengths; 128, 192 and 256 bits.
* Each round in AES is composed of: Byte Substitution, Mix Column and Key Addition.
* Number of rounds depends on the key length
    * 10 rounds for 128 bits
    * 12 round for 192 bits
    * 14 rounds for 256 bits
* Structure is based on substitution-permutation network.
* AES is the de facto world standard, it is more secure than DES.


Further reading: [AES Wikipedia](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)

## What is Asymmetric cryptography ?
It is a type of cryptography that uses keys. All users get two keys:

* One public key
* One private key

Users exchange their public keys to communicate with each other. Any user can encrypt a message as long as they have the receiver's public key. The message however, can only be decrypted by the receiver's private key. This is different than Symmetric cryptography, where only one key is used to both encrypt and decrypt. The blockchain uses asymmetric cryptography to achieve two goals:

* Identifying accounts (public keys)
* Authorizing transactions

## Bibliography
[[1.]](https://ucalgary-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01UCALG_ALMA51645328230004336&context=L&vid=UCALGARY&lang=en_US&search_scope=ONLINE_ONLY&adaptor=Local%20Search%20Engine&isFrbr=true&tab=everything&query=any,contains,basic%20cryptography&offset=0)Hans Delfs and Helmut Knebl. 2007. Introduction to Cryptography Principles and Applications. Second Edition. Berlin, Heidelberg: Springer.

[[2.]](https://www.youtube.com/watch?v=Sy0sXa73PZA) Ineapple. "DES Encryption by Hand", Youtube, August 26, 2017. Available: https://www.youtube.com/watch?v=Sy0sXa73PZA

[[3.]](https://www.tutorialspoint.com/cryptography/data_encryption_standard.htm) Tutorialspoint. Data Encryption Standard. Accesed on: June 7, 2020. [Online]. Available: http://libraryguides.vu.edu.au/ieeereferencing/webbaseddocument

[[4.]](https://www.geeksforgeeks.org/data-encryption-standard-des-set-1/) shubhamupadhyay. Data Encryption Standard | Set 1. geekforgeeks. Accessed on: June 16, 2020. Available: https://www.geeksforgeeks.org/data-encryption-standard-des-set-1/
