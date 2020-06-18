#### [Back](./README.md)

# Tor
When it comes to privacy, no part of the internet takes it more seriously than the dark web. The dark web is infamous for the various criminal acts that go on inside of it. But how does it work, how is it so anonymous, and how do you get on the dark web?

##   DNS Network Addressing
Standard web browsers are made to use DNS indexing to get access to a website. DNS indexing is what converts a website name to an IP address which your device can use to access the website, for example, if you were to type into your address bar '[Google.com](https://www.google.com)', it would direct you to the Google website. Then if you were to type into your address bar, '[216.58.217.46](http://216.58.217.46/)', it would also direct you to the Google website. This is because devices use IP addresses to find websites, they do not use human-readable names. Dark websites do not participate in DNS indexing, therefore it is impossible to access a dark website from your standard browsers, and can not be found by standard search engines[2]. To access a dark website, you need the right encryption and your web traffic needs to take a certain path to anonymize your connection. They use onion routing in selecting their paths.

## How Onion Routing works
<p style="text-align: center; margin-bottom:0; padding-bottom:0;"><image src=./images/tor1.png> </image> <image src=./images/tor2.png> </image> <image src=./images/tor3.png> </image></p>


<sub style="text-align:center;"> Images retrieved from: <a src =https://2019.www.torproject.org/about/overview.html.en> https://2019.www.torproject.org/about/overview.html.en</a> </sub>
</br></br></br>
When typing in a web address into the Tor browser, several steps occur before you get the website back. 


1. #### First, your computer sends a request to a directory authority server, the directory authority server will tell your computer about all the different routers on the Tor network, and the different paths that your computer may take to get to the website. 

1. #### Your computer decides on a specific route to take and send the encrypted data to the entry point router.

1. #### The data is encrypted again and routed through several middle point routers.

1. #### The data finally reaches the end point router, where the data is decrypted and sent out to the destination. 

1. #### Data continues moving back and forth between these routers and your computer and destination ensuring there is encryption between each router.


 **Directory Authority Servers:** These are just servers containing a periodically updating list of all the different routers/nodes on the Tor network, this allows a computer to decide on different paths to take to send its data[1].

**Entry Point:** This is the first router that your computer will communicate with, this router will have information about where the data is coming from, or in other words, it will know your IP address[3].

**Middle Point:** These are the majority of routers in the network, these are simply used to move encrypted data from one point to another[3].

**End Point:** These are computers at the end of the line, these are the ones that decrypt your information and make it readable by the destination. This is also the router that the destination thinks the data is coming from, in other words, this router is the IP address that the website receives. These end point routers have been known to be at risk of many legal issues and hosts of these routers often get prosecuted because of the legality of this process of providing false IP addresses[3].

## What makes this anonymous?
With this routing you can still access the regular web, however you will be far more anonymous as you do so. In onion routing, an individual router does not know anything about the network and data being passed around, except the router it received data from and the router it will send data to. This lack of information is useful in keeping the original computer's identity safe, ensuring as minimal knowledge about the original sender is being passed around the network as possible. Tor routers are volunteer-run, meaning any person can decide they want to host an end point, entry point, or middle point, and as long as they have the machinery to handle a large amount of data being passed around. The large majority of the people involved in this operation are strict advocates for online privacy and freedom of information, however, there are often researchers and nefarious individuals who will make an end point router and spy on the decrypted data coming out of the end of the network.

## Bibliography
[[1]](https://metrics.torproject.org/glossary.html) “Glossary,” *Tor Metrics*. [Online]. Available: https://metrics.torproject.org/glossary.html. [Accessed: 18-Jun-2020].

[[2]](https://www.extremetech.com/internet/245086-deep-dive-dark-web-how-to-use) 2017 at 11:15 am C. Jessica Hall on March 1, “ExtremeTech explains: All about the dark web, and how to use it,” *ExtremeTech*, 01-Mar-2017. [Online]. Available: https://www.extremetech.com/internet/245086-deep-dive-dark-web-how-to-use. [Accessed: 16-Jun-2020].

[[3]](https://trac.torproject.org/projects/tor/wiki/TorRelayGuide) “Tor Relay Guide,” *The Tor Project*. [Online]. Available: https://trac.torproject.org/projects/tor/wiki/TorRelayGuide. [Accessed: 16-Jun-2020].


## Further Readings
* [More Information about how Tor operates](https://en.wikipedia.org/wiki/Tor_(anonymity_network)#:~:text=Tor%20aims%20to%20conceal%20its,by%20volunteers%20around%20the%20globe.)

* [Tor Documentation and News](https://2019.www.torproject.org/docs/documentation.html.en)