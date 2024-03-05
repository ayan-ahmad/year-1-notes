## Overview
![[Network Architecture.png]]
### Link Layer
The link layer of the Internet Architecture is the lowest to the physical equipment, it transmits data using a wire, a fibre optic cable, a radio signal.
## IP Layer
Determines the destination for the outbound packet to end up
## IP Addresses
IP addresses are assigned to every computer based on where and what network they are connected to.
### IPv4
The old IPv4 was 32bits but later we found out this would not be enough:
`43.27.231.79`
## IPv6
The new IPv6 address is 128 bits allowing for more possible values:
`2001:930:30:60e0::2178`
## Domain Name System (DNS)
The DNS is a resolver which given a domain will return the IP for it.
It's sort of like asking for directions for getting to UofG and they give you the route the address of the nearest university building.
### Transmission Control Protocol (TCP)
This controls the reconstruction of the packets once they are received at the destination using the offsets given
### Ports
Whenever a message is sent we need to prompt which port we want to connect with as each port will have a different application and rules. This is done by putting the port after the address, e.g.: `localhost:8080`
### Application Layer
A client application communicates with a server application using protocols.
The most common protocol we use is HTTP(s). You can denote this by adding it before the address: `http://localhost`
### HTTP
HTTP is the most dominant application layer protocol. The way it works is by:
1. Make the connection
2. Request a document
3. Retrieve the document
4. Close the connection
## Managing Received Data
When managing the received data ensure that all data is visible and clear to the end user.
## HTML
When the client requests a page the server responds with the HTML document if it exists.
The received data is parsed by the browser and displayed to the user and sent to the DOM
The Document Object Model (DOM), represents the HTML document as a tree
