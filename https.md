# Browsing the internet securely: HTTP, HTTPS and TLS 

Browsing websites is a common activity and one of the main protocols facilitating it is HTTP or HyperText Transfer Protocol. HTTP is all about messages being sent between clients and servers. Clients usually request things from servers and servers are supposed respond to those requests accordingly. HTTP by itself is not secure from hackers though so HTTPS adds security. The 'S' stands for secure. HTTPS uses TLS or Transport Layer Security to create security. This article will explain how TLS creates security and how it deals with attacks.

## HTTP and HTTPS
When you open an internet browser and navigate to your favourite website what is happening is your browser is requesting the websites server to send you the page of you website. To do this HTTP is the protocol your browser follows. HTTP has rules of what a request and response looks like. As long as HTTP rules are followed your browser will be able to browse websites with no issues.

Of course HTTP by itself does not have any sort of security built-in. A hacker could eavesdrop on HTTP connections and also change what is being sent and recieved. This is where HTTPS comes in and makes sure a hacker cannot do anything. Which leads us to how TLS makes HTTPS secure.

## TLS
TLS used be what was called SSL or Secure Sockets Layer. This protocol guarantees that data between client and servers has privacy and has integrity. Privacy as in only those allowed can know what the data contains and integrity to know whether the data was changed in anyway. TLS has two layers: the TLS handshake protocol and the TLS record protocol.

### TLS handshake protocol
The handshake is meant to authenticate a server with a client i.e. your internet browser. With HTTPS your browser initiates a handshake when connecting to a website. For this article we will be looking that handshake of TLS 1.2 and TLS 1.3. The 1.3 handshake is more secure and faster then 1.2. Below are the steps of the handshake.

#### TLS 1.2
1. Client sends hello to the server. Hello's contain a random number and a list of protocols and cipher suites the sender knows.
2. Server sends hello and its certificate to the client. Server picks the strongest protocol and the best cipher suite that both parties can use.
3. Client sends a ClientKeyExchange, ChangeCipherSpec, and a finished message to the server. 
4. Server sends a ChangeCipherSpec and finished messaged. 
5. Both the client and server change to the cryptographic protocol picked by the server and regular HTTP traffic begins under that protocol.

#### TLS 1.3
1. Client sends hello and keyshare to server.  Hello's contain a random number and a list of protocols and cipher suites the sender knows.
2. Server sends hello, keyshare, certificate, CertificateVerified and finished to the client.
3. Both the client and server change to the cryptographic protocol picked by the server and regular HTTP traffic begins under that protocol.

![tls handshake](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/tls12vstls13.png)
source: https://calcomsoftware.com/wp-content/uploads/2019/03/tls12-vs-tls13-1024x549.png

Let's breakdown what some of the terms used above mean.
* The random number in the hello will be used to create new shared key for both the client and server to use after the handshake.
* Protocols listed would include what version of TLS each support.
* Cipher suites are the mathematical techniques for cryptography each party can use.
* A certificate is piece of information that tells the client that this server can be trusted. Certificates are supposed to be from 3rd parties that the client can verify trust with.
* ClientKeyExchange is another number from the client that is encrypted using a key from the certificate before being sent to the server. The server has a key to reveal the encrypted number. 
* ChangeCipherKey tells the recipient to switch to the encryption decided upon by the server.
* Both client and server send the finished message encrypted with the chosen encryption.
  
It should be noted that a new key called the session key is generated from the random numbers in hello and the ClientKeyExchange number. That key is the shared key for the encryption used for the finished message and HTTP traffic later.

* A keyshare is another random number used for generating the new shared key.

As illustrated by the graphic TLS 1.3 is faster than TLS 1.2.

 TLS 1.3 is more secure than TLS 1.2 because the allowed cipher suites was modified to disallow certain suites that have discovered to be weak and certain Diffie Hellman numbers were blacklisted. Also the handshake is verified to check if any message was tampered with.

### TLS record protocol
The record protocol is for encrypting and authenticating data sent between client and server. The encryption used is chosen during the handshake.

## Attacks agaisnt TLS














