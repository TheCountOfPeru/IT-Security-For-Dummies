[[Back]](./README.md)
# Browsing the internet securely: HTTP, HTTPS and TLS 

Recommended knowledge: basic cryptography, networking

When you use an internet browser to visit your favourite websites data is being sent across the internet. How the data is being secured will be explained in this article.

## HTTP and HTTPS
When you open an internet browser and navigate to your favourite website what is happening is your browser is requesting the websites server to send you the page of your requested website. To do this HTTP or Hyper Text Transfer Protocol is the protocol your browser follows when sending messages for requests. HTTP is the rules of what a request and response message looks like. As long as HTTP rules are followed your browsers and websites can communicate.

HTTP by itself does not have any sort of security built-in though. A hacker could eavesdrop on HTTP connections and/or change what is being sent and recieved. This is where HTTPS comes in and makes sure a hacker cannot do anything. This is the secure version of HTTP as denoted by the 'S'. The mechanism responsible for creating security is called TLS.

## TLS
TLS or Transport Layer Security is a protocol guarantees that data between client and servers has privacy and has integrity. Privacy refers to only those allowed can know what the data represents and integrity refers to being able to know if the data was changed in anyway. TLS has two layers: the TLS handshake protocol and the TLS record protocol.

### TLS handshake protocol
The handshake is meant to authenticate a server with a client i.e. your internet browser so that you know you are connecting to a trusted website also initiates the security terms the two will communicate on. With HTTPS your browser initiates a handshake when connecting to a website. For this article we will be looking at the handshake of TLS 1.2 and TLS 1.3. The 1.3 handshake is more secure and faster then 1.2 but not everyone uses 1.3 yet. Below are the steps of the handshake.

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
  
It should be noted that a new key called the session key is generated from the random numbers in hello and the ClientKeyExchange number. That key is the shared key for the encryption used for the finished message and HTTPS traffic later.

* A keyshare is another random number used for generating the new shared key.

As illustrated by the graphic TLS 1.3 is faster than TLS 1.2.

TLS 1.3 is more secure than TLS 1.2 because the allowed cipher suites was modified to disallow certain suites that have discovered to be weak and certain Diffie Hellman numbers were blacklisted. Also the handshake is verified to check if any message was tampered with.

### TLS record protocol
The record protocol is for encrypting and authenticating data sent between client and server. The encryption used is chosen during the handshake. Authenticating is facilitated by MAC or Message Authentication Checksum. This means that when a message is ready to be sent a MAC is calculated on the message. Then the MAC and message is encrypted together with the checksum. Then the result is sent. When the result is recieved it decrypted then calculates the MAC and compares to MAC included with the message. If they match up the message is sent to the program who was meant to recieve it. The keys used for encrytion are from the handshake step. 

## Attacks agaisnt HTTPS
Actually decrypting a HTTPS connection is more trouble than it's worth. Instead tricking browsers to not to not use HTTPS is a much more feasible attack.

First, websites can use various methods to move a client from a HTTP connection to HTTPS automatically. What an attacker needs to do is get in between that action.

A common attack is the where the attack is sitting between the messages of the client and server. Example steps are as follows:

1. The client sends a request for HTTP url and it goes through the attacker which sends the same request but as HTTPS to the server.
2. The server sends the HTTPS response to the attacker. The attacker modifies the response to HTTP and sends it to the client. 

Now the client has a HTTP connection to the attacker even though it thinks it has connection with the server. And the server thinks it has a HTTPS connection to the client.

There are two solutions to beat this.
1. Force your browser to only use HTTPS. For example installing the HTTPS Everyone browser extension available for Chrome, Firefox, and Opera.
2. Have a server implement HSTS or HTTP Strict Transport policy. This adds a header to all server replies saying that this page should only be accessed by HTTPS. A browser would see that and refuse to display the requested page if on a HTTP connection.

## Further topics for reading
* certificates 














