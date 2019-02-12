# Why & What

## What is a bridge?

A **bridge** is a device that separates two or more network segments within one logical network \(e.g. a single IP-subnet\). The job of the bridge is to examine the destination of the data packets one at a time and decide whether or not to pass the packets to the other side of the Ethernet segment. The result is a faster, quieter network with less collisions.  In the OSI model bridging acts in the first two layers, below the network layer.

## Why we need the client bridge mode?

Because we want to connect a layer2 network segment behind the wireless client to the layer2  network segment of the wireless AP. The typical scenario is shown below.

![A scenario of the client bridge mode](.gitbook/assets/image.png)

## Client bridge mode issues

Client bridge mode could not be used via standard client mode in Linux due to the limitation of the 802.11 protocol.

![Problem using standard client mode for bridging](.gitbook/assets/image%20%281%29.png)

The 802.11 standard only uses three MAC addresses for frames transmitted between the Access Point and the Station. Frames transmitted from the Station to the AP don't include the Ethernet source MAC of the requesting host and response frames are missing the destination Ethernet MAC to address the target host behind the client bridge.

