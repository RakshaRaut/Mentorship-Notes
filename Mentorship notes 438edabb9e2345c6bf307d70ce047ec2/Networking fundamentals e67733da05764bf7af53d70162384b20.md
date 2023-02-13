# Networking fundamentals

A web application (web app) is **an application program that is stored on a remote server and delivered over the internet through a browser interface.**

- These are three basic security properties that come up often in classical information security. They are often referred to the CIA triad.
1. **Confidentiality**: Permission is required to read data and communications.
2. **Integrity**: Permission is required to manipulate data and communications.
3. **Availability**: Data and communications are accessible to the user.
It will be useful to keep these properties in mind as we discuss different types
of network attacks.
Network attacks can be categorized into a few broad types as listed below
from most local to least local:
4. **Physical Access**: The attacker has physical access to the network.
5. **In Path/Man in the Middle:** The attacker is between a communicator
and the intended recipient and can see, add, and block packets.
6. **On Path/Man on the Side:** The attacker can only see, add, and potentially copy packets.
7. **Passive:** The attacker can only see network traffic.
8. **Off Path:** The attacker can’t see network traffic, but can potentially send
data.
Here are the layers of the OSI model that we’ll be focusing on:
9. Application (e.g. DNS, HTTP, HTTPS)
10. Transport (e.g. TCP, UDP)
11. Network (e.g. IP, BGP)
- **physical and link layer threats**
    
    1.Eavesdropping;
    Eavesdropping is an example of an attack on the physical layer. It is passive attack that violates confidentiality.
    
    Attacker can gain access to the network include:
    
    - Connecting to an unprotected WiFi network.
    - An attacker exploits a well known security vulnerability in WPA2 to learn
    the network password and connect to the network.
    
    2.Injection;
    
    Injection is an active form of attack that takes place on the physical and link layers.
    
    3.Jamming;
    Jamming is an attack that prevents signals from reaching their destination.
    Jamming attacks violate the goal of availability.
    
    # Network Threats
    
    - Spoofing
    - Constructing Arbitrary Network Packets
        - Network Scanning
        - Denial of Service
    - Misdirection
    
    **TCP threats(Transmission Control Protocol);**
    
    TCP) sessions are identified by a source address, source port, destination address, and destination port, and that each TCP packet contains a sequence number that determines where in the stream it belongs. Attackers can exploit these pieces of information to tamper with TCP connections. One way an attacker can tamper with a TCP connection is called on-path
    injection.