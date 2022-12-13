# Netpractice

![alt text](https://github.com/aoumad/Netpractice/blob/main/images/Grade.png)

## Introduction

This project will help us discover networking through practical cases.We will have to configure small networks thoughout 10 exercises of 10 different levels of difficulty.

But before that, we need to understand some basic networking concepts that will allow us solving the exercises easily, Shall we start ?

## Table of Contents
  - [TCP](wWhat-is-a-tcp)
  - [IP address](#ip-address-network-layer)
  - [Subnet mask](#subnet-mask)
  - [Switch](#switch)
  - [Router](#router)
- [Levels](#levels)
- [Important Resources](#resources)

---
## What is a TCP
TCP/IP, in full **Transmission Control Protocol/Internet Protocol**, standard Internet communications protocols that allow digital computers to communicate over long distances.

The Internet is a packet-switched network, in which information is broken down into small packets, sent individually over many different routes at the same time, and then reassembled at the receiving end.

TCP is the component that collects and reassembles the packets of data, while IP is responsible for making sure the packets are sent to the right destination. TCP/IP was developed in the 1970s and adopted as the protocol standard for ARPANET (the predecessor to the Internet) in 1983

### How does TCP/IP works?
- TCP/IP job is to divide the different communication tasks into layers, each layer has a different function. Data goes through 4 individual layers before it is received on the other hand, TCP/IP then goes through these layers in reverse to reassemble the data and represent it to the reciepent.

### What is the difference between OSI MODEL and TCP/IP model?

- The OSI model is more widely known and used than the TCP/IP model. The OSI model is the standard model for understanding how communication takes place over a network, and is used in a variety of different contexts, including education, research, and standardization. The TCP/IP model, on the other hand, is primarily used in the implementation of the Internet and other networks that use the Internet Protocol (IP).
- The OSI model and the TCP/IP model are both standardized models that are used to help understand how communication takes place over a network. While there are some similarities between the two models, there are also some key differences.

![alt text](https://github.com/aoumad/Netpractice/blob/main/images/OSI%20vs%20TCP:IP.png)

> The OSI model, or the 'Open Systems Interconnection model', is a framework that was developed by (ISO) to help understand how different systems communicate with each other over a network. The OSI model is a seven-layer model, with each layer representing a different aspect of network communication.

> The TCP/IP model, on the other hand, is a four-layer model that was developed by DoD (US departement of defense) to help understand how communication takes place over the Internet. The TCP/IP model is sometimes referred to as the internet model because it is the foundation of internet

|TCP/IP	|OSI |
|:-:	|:--    |
|TCP refers to Transmission Control Protocol | OSI refers to Open Systems Interconnection|
|TCP/IP has 4 layers | OSI has 7 layers |
|TCP/IP is more reliable | OSI is less reliable|
|TCP/IP does not have very strict boundaries | OSI has strict boundaries |
| TCP/IP follows a horizontal approach | OSI follows a vertical approach |
| Functions of each layer are more general | Each layer has a specific set of functions |
| Transport layer in TCP/IP does not provide assurance delivery of packets | in OSI model, transport layer provides assurance delivery of packets |
| Focuses on how communication takes place over the network | Focuses on how different systems communicate with each other over a network |

---
## IP Address: Network Layer

Networks don’t work without addresses: Whenever you are sending something, you need to specify where it should go and where it came from.

An IP address is a unique address that identifies a device on the internet or a local network. IP stands for "Internet Protocol," which is the set of rules governing the format of data sent via the internet or local network.

In essence, IP addresses are the identifier that allows information to be sent between devices on a network: they contain location information and make devices accessible for communication. The internet needs a way to differentiate between different computers, routers, and websites. IP addresses provide a way of doing so and form an essential part of how the internet works.

![alt text](https://github.com/aoumad/Netpractice/blob/main/images/Public-vs-local-IP-addresses.png)

## What is the difference between private IP address and public IP address?
- A private IP address is a non-routable address that is used for a local networks, such as a home or office network. Private IP addresses are not accessible from the internet, and are therefore considered more secure than public IP addresses. Private IP addresses are typically in the range of 192.168.0.0 to 192.168.255.255 or 10.0.0.0 to 10.255.255.255.
- In contrast, a public IP address is a globally unique address that is assigned to a device by an internet service provider (ISP) in order to provide access to the internet. Public IP adresses are routable, which means they can be accessed from anywhere on the internet. Public IP addresses are typically assigned to servers, routers, and other devices that need to be accessible from the internet.
- In summary, the main difference between private and IP public IP addresses is that private IP addresses are not accessible from the internet, while public IP addresses are. This makes private IP addresses more secure, but also more limited in terms of their functionality.

#### IPv4 Addresses and 32-bit Numbers
IP addresses are just 32-bit binary numbers, but they’re important binary numbers: you need to how to work with them. When working with subnet masks, new network administrators generally get confused with the ones they haven’t memorized. All the subnet mask amounts to is moving the boundary between the part of the address that represents a "network" and the part that represents a "host." Once you’re comfortable with this method of thinking about IP addresses and masks, you’ve mastered IP addressing.

Binary is quite simple. In binary the only numbers are zeros and ones, and a 32-bit number holds 32 zeros and ones. We’re all used to base-10 numbers, where each place in a number can hold any number from 0-9. In binary each place holds either a zero or a one. Here’s the address 255.255.255.0 in binary:

11111111.11111111.11111111.00000000

For convenience, network engineers typically break IP addresses into four 8-bit blocks, or octets. In an 8-bit number, if all of the bits are set to 1, then the number is equal to 255. In the previous address, 11111111 represents 255 and 00000000 represents zero.

---
### Subnet Mask

Subnet Mask is a 32-bit number that is used to partition IP addresses into a network ID and a host ID. Subnet masks are used by TCP/IP services and applications to determine whether a given IP address on an internetwork is a local network address or a remote network address.

#### How it works?
Subnet masks are represented as four-octet dotted-decimal numbers, just as IP addresses are, except that the most common values for an octet in a subnet mask are 0 and 255. In binary notation, decimal 0 represents the octet 00000000, and decimal 255 represents 11111111.

A subnet mask consists of 32 binary digits, the first n of which are 1s and the remaining of which are 0s. When the subnet mask is logically ANDed with a 32-bit IP address of a TCP/IP host, the result is the network ID of the host – the portion of the host’s IP address that identifies which network the host is on. When the inverse of the subnet mask (for example, NOT mask) is logically ANDed with the IP address of the host, the result is the host ID of the host – the portion of the host’s IP address that uniquely identifies the host on its network.

For example, consider the IP address 207.61.16.119 and the subnet mask 255.255.255.0. Converting these two numbers to binary and ANDing them gives the host’s Network ID:
```
Host = 11001111 00111101 00010000 01110111
Mask = 11111111 11111111 11111111 00000000
AND  = 11001111 00111101 00010000 00000000
     = 207.61.16.0 = network ID
```

#### IP Adress Classes and Subnet Mask

Since the internet must accommodate networks of all sizes, an addressing scheme for a range of networks exists based on how the octets in an IP address are broken down. You can determine based on the three high-order or left-most bits in any given IP address which of the five different classes of networks, A to E, the address falls within.

(Class D networks are reserved for multicasting, and Class E networks not used on the internet because they are reserved for research by the Internet Engineering Task Force IETF.)

A Class A subnet mask reflects the network portion in the first octet and leaves octets 2, 3, and 4 for the network manager to divide into hosts and subnets as needed. Class A is for networks with more than 65,536 hosts.

A Class B subnet mask claims the first two octets for the network, leaving the remaining part of the address, the 16 bits of octets 3 and 4, for the subnet and host part. Class B is for networks with 256 to 65,534 hosts.

In a Class C subnet mask, the network portion is the first three octets with the hosts and subnets in just the remaining 8 bits of octet 4. Class C is for smaller networks with fewer than 254 hosts.

Class A, B, and C networks have natural masks, or default subnet masks:

```
Class A: 255.0.0.0
Class B: 255.255.0.0
Class C: 255.255.255.0
```

You can determine the number and type of IP addresses any given local network requires based on its default subnet mask.

---

### Switch

![alt text](https://github.com/aoumad/Netpractice/blob/main/images/switch.png)

A switch is a hardware component in network infrastructure that performs the switching process. The switch connects network devices, such as computers and servers, to one another. 

A switch enables multiple devices to share a network while preventing each device's traffic from interfering with other devices' traffic. The switch acts as a traffic cop at a busy intersection. When a data packet arrives at one of its ports, the switch determines which direction the packet is headed. It then forwards the packet through the correct port for its destination.

Some data packets might come to the switch from devices, like computers or voice-over-IP (VoIP) phones, that are attached directly to it. Other data packets might come to the switch from indirectly connected devices, through a network element such as a hub or router. 

The switch knows which of the network's devices are connected to it, and it can transfer data packets between those devices directly. In other cases, data packets may be going to more-distant destinations, on other networks. A switch in such a scenario forwards the packets to a router, which then forwards them to their destinations on the network. 
