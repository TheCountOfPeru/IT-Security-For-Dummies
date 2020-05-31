
Briefing on firewalls


## Introduction

Generally, firewalls are considered as a protection against unauthorized interactive actions from the outside world. This stops those hackers from breaking into machines on your network. More complicated firewalls block access from the outside to the internal part, but permit users on the inside to communicate a little more freely with the outside.
Firewalls is important also because it provides its users with an important logging and confirming function; this is very significant to the administrator to know what type/volume of traffic that has been processed through it. 



In general, there are two types of firewalls:


1.	Network layer

2.	Application layer

The difference is very subtle. The categorization depends on what mechanisms the firewall uses to go through from one protected network to another. The International Standards Organization (ISO) Open Systems Interconnect (OSI) model for networking defines seven levels, where each level provides services that higher levels depend on. It’s important to bear in mind that the lower-level the mechanism, the less secure the firewall is.


## Formal definition:


A firewall is simply a system designed to prevent unauthorized access to or from a private network. Firewalls can be implemented in both hardware and software, or a combination of both. Firewalls are frequently used to prevent unauthorized Internet users from accessing private networks connected to the Internet. All data entering or leaving the Intranet pass through the firewall, which examines each packet and blocks those that do not meet the specified security criteria.


## Network layer firewalls

One important feature of network layer firewalls is that they allow traffic to go directly through them, so to use them you either need to have a valid IP address, or a private internet address. The network layer firewalls are usually very fast and almost invisible to its users.
This type of firewalls makes its decisions based on the IP address, destination address and ports in individual IP packets. A simple router is the traditional network layer firewall, since it is not able to make particularly complicated decisions about what a packet is actually talking to or where it actually came from. Modern network layer firewalls have become increasingly more sophisticated, and now maintain internal information about the state of connections passing through them at any time.


## Application layer firewalls

An application layer firewall may influence performance and may make the firewall less transparent. Early application layer firewalls are not transparent to terminal-users and requires some training to use. However, later, modern application layer firewalls are often totally transparent. Application layer firewalls provide more detailed checking reports, and they enforce more reliable security mechanism than network layer firewalls.
The future of firewalls in everyday use sits somewhere between both network layer firewalls and application layer firewalls. It is likely that network layer firewalls will become increasingly aware of the information going through them, and application layer firewalls will become more and more transparent. The end result will be kind of a fast packet-screening system that logs and checks data as it passes through.


## Quick view:

main points:

•	A firewall is a hardware or software system that prevents unauthorized access to or from a network.

•	Two main types of firewalls: network layer and application layer

•	Network layer firewalls make decisions based on the source address, destination address and ports in individual IP packets.

•	Application layer firewalls generally are hosts running proxy servers, which permit no traffic directly between networks and perform elaborate logging and examination of traffic.

