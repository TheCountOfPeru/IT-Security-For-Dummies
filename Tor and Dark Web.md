# The Dark Web and Tor
When it comes to privacy, there is no part of the internet that takes it more seriously than the dark web. The dark web is infamous for the various criminal acts that go on inside of it. But how does it really work, how is it so anonymous, and how do you get on the dark web?

## Accessing The Dark Web
To gain access to the dark web, you will need a special browser, known as Tor. The two key differences in websites on the dark web and regular web is that they are not indexed by search engines like Google, and can not be accessed by regular web browsing software. This is due to the fact that the dark web is hosted on overlay networks, these networks are connected to the internet and are the same as the regular web under the hood. They use the same technology behind webpages and their assets, but a different network addressing system.

##   DNS Network Addressing
Standard web browsers are made to use DNS indexing to get access to a website. DNS indexing is what converts a website name to an IP address which your device can use to access the website, for example, if you were to type into your address bar '[google.com](google.com)', it would direct you to the google website. Then if you were to type into your address bar, '[216.58.217.46](216.58.217.46)', it would also direct you to the google website. This is because devices actually use IP addresses to find websites, they do not use the human readable names. Dark websites do not participate in DNS indexing, therefore it is impossible to access a dark website from your standard browsers, and can not be found by standard search engines. To access a dark website, you need the right encryption and your web traffic needs to take a certain path to anonymize your connection. They must use onion routing in selecting their paths.

## How Onion Routing works
<p style="text-align: center;"><image src=./images/tor1.png> </image> <image src=./images/tor2.png> </image> </p>
<p style="text-align: center;"> <image src=./images/tor3.png> </image> </p>

When typing in a web address into the Tor browser, several steps occur before you get the website back. 


1. #### First your computer sends a request to a directory authority server, the directory authority server will tell your computer about all the different routers on the Tor network, and the different paths that your computer may take to get to the website. 

1. #### Your computer decides on a specific route to take and send the encrypted data to the entry point router.

1. #### The data is encrypted again and routed through several middle point routers.

1. #### The data finally reaches the end point router, where the data is decrypted and sent out to the destination. 

1. #### Data continues moving back and forth between these routers and your computer and destination ensuring there is encryption between each router.


 **Directory Authority Servers:** These are just servers containing a periodically updating list of all the different routers/nodes on the Tor network, this allows a computer to decide on different paths to take to send its data.

**Entry Point:** This is the first router that your computer will communicate with, this router will have information about where the data is coming from, or in other words, it will know your IP address.

**Middle Point:** These are majority of routers in the network, these are simply used ot move encrypted data from one point to another.

**End Point:** These are computers at the end of the line, these are the ones that decrypt your information and make it readable by the destination. This is also the router that the destination thinks the data is coming from, in other words, this router is the IP address that the website receives. These end point routers have been known to be at risk of many legal issues and hosts of these routers often get prosecuted because of the legality of this process of providing false IP addresses.

## What makes this anonymous?
An individual router has no knowledge about the data other than the router it received data from and the router it will send data to. This lack of information is useful in keeping the original computers identity safe, ensuring as minimal knowledge about the original sender is being passed around the network as possible. Tor routers are volunteer run, meaning any person can decide they want to host an end point, entry point or middle point, and as long as they have the machinery to handle the large amount of data being passed around. The large majority of the people involved in this operation are strict advocates for online privacy and freedom of information, however there are often researchers and nefarious individuals who will make an end point router and spy on the decrypted data coming out of the end of the network.

## Further Readings
* [More Information about how Tor operates](https://en.wikipedia.org/wiki/Tor_(anonymity_network)#:~:text=Tor%20aims%20to%20conceal%20its,by%20volunteers%20around%20the%20globe.)

* [Tor Documentation and News](https://2019.www.torproject.org/docs/documentation.html.en)