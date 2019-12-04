# The OSI model

The OSI model is a way to split up the different parts that make 2 computer
communicate together, from the physical level (the actual signal) to the
end-user interface (the browser for example). There are 7 different layers.

Other models exists, such as `TCP/IP`.

## Vocabulary

Node
> A computer on a network

Protocol
> A set of conventions, standards.

## Layer 1 - Physical

> Convert bits to a signal, and vice-versa

The shape of the signal is basically defined here. The frequency, usually 5 GHz
or 2.4 GHz for wireless devices.

In this layer, we have network cards, hubs, modems, etc...

## Layer 2 - Data Link

> Establishes protocols that the physical devices have to use.

This layer defines the protocol with which the physical layer is
going to establish, exchange and close connections.

For wireless, the protocol 802.11 is most commonly used. For Ethernet, it's
802.3.

### About 802.11

802.11 is group of protocols maintained by the Institute of Electrical and
Electronics Engineers (IEEE). It was created in 1997, so there has been several
updates. Here are the different protocols, ranked from best to shittiest:

`802.11ac`
`802.11n`
`802.11g`
`802.11b`

## Layer 3 - Network Layer

This is where we send packets over the network, and **external networks**.

The most commonly used protocol here is Internet Protocol (IP). It makes sense:
inter net → connections between multiple networks.

From one IP, you can contact any computer (not hidden)!

This protocol will deliver *packets* (messages) either directly, or by using
intermediate nodes

## References

Probably a good idea to look over here:
<https://en.wikipedia.org/wiki/OSI_model>

Good resource (with so much other stuff): <http://www.linfo.org/>
