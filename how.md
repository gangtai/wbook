---
description: ARP-NAT
---

# How \(mechanism\)

## Intro 

**ARPNAT** has similar idea as NAT for IP networks, except that NAT works one layer deeper. Instead of translating IP address, the wireless client translates between the MAC address on side of it by a IP-MAC mapping table. That's why ARPNAT is also called MAC Address Translation\(MAT\). There are three types of frames/packets need to be translated by MAT: IP unicast, ARP, and DHCP offer. 

![illustration of ARP-NAT mechanism](.gitbook/assets/image%20%282%29.png)

### ARP

#### Outbound \(Ethernet to WiFi\) \(Client to AP\)

* Learn/record a new entry by the IP and MAC in the incoming ARP frames\(SHA/SPA\) to the IP-MAC table.
* Translate Ethernet SA and ARP SHA by client's MAC.

#### Inbound \(WiFi to Ethernet\) \(AP to client\)

* Translate Ethernet DA and ARP THA by the looked up MAC with ARP TPA.

### IP unicast

#### Outbound \(Ethernet to WiFi\) \(Client to AP\)

* Translate Ethernet SA by client's MAC.

#### Inbound \(WiFi to Ethernet\) \(AP to client\)

* Translate Ethernet DA by the looked up MAC with Destination IP Address.
* If it can’t be looked up then broadcast the frame.

### DHCP offer

#### Inbound \(WiFi to Ethernet\) \(AP to client\)

* Translate Ethernet DA by CHADDR in the DHCP offer.





