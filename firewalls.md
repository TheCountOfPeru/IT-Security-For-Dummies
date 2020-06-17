
#Briefing on firewalls


## Introduction



A firewall is simply a system designed to prevent unauthorized access to or from a private network. Firewalls can be implemented in both hardware and software, or a combination of both. Firewalls are frequently used to prevent unauthorized Internet users from accessing private networks connected to the Internet. All data entering or leaving the Intranet pass through the firewall, which examines each packet and blocks those that do not meet the specified security criteria.

Generally, firewalls are considered as a protection against unauthorized interactive actions from the outside world. This stops those hackers from breaking into machines on your network. More complicated firewalls block access from the outside to the internal part, but permit users on the inside to communicate a little more freely with the outside.

Firewalls is important also because it provides its users with an important logging and confirming function; this is very significant to the administrator to know what type/volume of traffic that has been processed through it. 



In general, there are two types of firewalls:


1.	Network layer

2.	Application layer

The difference is very subtle. The categorization depends on what mechanisms the firewall uses to go through from one protected network to another. The International Standards Organization (ISO) Open Systems Interconnect (OSI) model for networking defines seven levels, where each level provides services that higher levels depend on. It’s important to bear in mind that the lower-level the mechanism, the less secure the firewall is.





## Network layer firewalls

One important feature of network layer firewalls is that they allow traffic to go directly through them, so to use them you either need to have a valid IP address, or a private internet address. The network layer firewalls are usually very fast and almost invisible to its users.
This type of firewalls makes its decisions based on the IP address, destination address and ports in individual IP packets. A simple router is the traditional network layer firewall, since it is not able to make particularly complicated decisions about what a packet is actually talking to or where it actually came from. Modern network layer firewalls have become increasingly more sophisticated, and now maintain internal information about the state of connections passing through them at any time.


## Application layer firewalls

An application firewall is a form of firewall that controls input, output, and/or access from, to, or by an application or service. It operates by monitoring and potentially blocking the input, output, or system service calls.

 This is done by examining information passed through system calls instead of or in addition to a network stack. A host-based application firewall can only provide protection to the applications running on the same host.




