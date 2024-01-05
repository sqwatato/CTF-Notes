https://play.picoctf.org/practice/challenge/286

- open pcap file in wireshark
- [[Packet Analysis]] is all about filtering
![[Screenshot 2024-01-03 at 6.41.38 PM.png]]
- flag is unlikely to be in ARP ([[Address Resolution Protocol]])
	- filter out arp messages with `!arp`
![[Screenshot 2024-01-03 at 6.41.51 PM.png]]
- flag won't be in the first 3 since they are a [[TCP Handshake]]
- For the other 2 packets, one has the `PSH` flag set, meaning there is data in the packet
- clicking on the packet, in the packet bytes pane you will see the flag
![[Screenshot 2024-01-03 at 6.48.21 PM.png]]