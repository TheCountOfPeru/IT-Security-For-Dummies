# Browsing the internet securely: HTTP, HTTPS and TLS 

Browsing websites is a common activity and one of the main protocols facilitating it is HTTP or HyperText Transfer Protocol. HTTP is all about messages being sent between clients and servers. Clients usually request things from servers and servers are supposed respond to those requests accordingly. HTTP by itself is not secure from hackers though so HTTPS adds security. The 'S' stands for secure. HTTPS uses TLS or Transport Layer Security. This article will explain how TLS creates security.

## HTTP and HTTPS
When you open an internet browser and navigate to your favourite website what is happening is your browser is requesting the websites server to send you the page of you website. To do this HTTP is the protocol your browser follows. HTTP has rules of what a request and response looks like. As long as HTTP rules are followed your browser will be able to browse websites with no issues.

Of course HTTP by itself does not have any sort of security built-in. A hacker could eavesdrop on HTTP connections and also change what is being sent and recieved. This is where HTTPS comes in and makes sure a hacker cannot do anything. Which leads us to how TLS makes HTTPS secure.

## TLS
TLS used be what was called SSL or Secure Sockets Layer. This protocol guarantees that data between client and servers has privacy and has integrity. Privacy as in only those allowed can know what the data contains and integrity to know whether the data was changed in anyway. TLS has two layers: the TLS handshake protocol and the TLS record protocol.

### TLS handshake protocol
The handshake is meant to authenticate a server with a client i.e. your internet browser. With HTTPS your browser initiates a handshake when connecting to a website. For this article we will be looking that handshake of TLS 1.2 and TLS 1.3. 1.3 fixes some problems with 1.2. The 1.3 handshake is more secure and faster then 1.2

![tls handshake](https://github.com/TheCountOfPeru/IT-Security-For-Dummies/blob/master/images/tls12vstls13.png)


