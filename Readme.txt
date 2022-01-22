=== OSI Model ===
Application -   Telnet, SMTP, FTP
Presentation -  Format Data, Encryption
Session -       Start, stop session
Transport -     TCP/UDP, Port number
Network -       IP, routers
Data -          MAC address, switches
Physical -      Ethernet, Cables

=== TCP/IP ===
Application ( Data ) - SMTP, FTP, HTTP
Transport ( Segment = TCP/UDP header + data ) - Add TCP header ( Port numbers etc )
Network ( Packet = ip + segment ) -  Add source destination ip addresses
Data Link ( Frame = header + packet + tailer ) - Add MAC address . Adds header and tailer.
Physical - Cables

=== TCP ===
Transmission control protocol
1) More reliable
2) Connection oriented protocol - i.e. Connection has to be establised between sender and receiver before sending data. Also to end the session.
3) Used when data loss is not allowed. Latency is fine.
4) Header ( 20 - 60 bytes ) - Given below.
5) Packets are ordered using sequence number.
6) Possible to retransmit last packets.
7) FTP, HTTP, SMTP, HTTPS, Telnet

Connection is done via 3 way handshake
SYN, SYN-ACK, ACK

=== UDP ===
User Datagram protocol
1) Unreliable
2) Connectionless Datagram oriented protocol
3) Used where latency should be minimum. Loss of data is fine. Video call, gaming 
4) Header ( Fixed 8 bytes )- Source port, destination port, length, checksum
5) No sequencing.
6) No retransmission of lost packets
7) DHCP, DNS, TFTP, RIP, VoIP, 

=== Headers ===
<-- 16 bits -->  <-- 16 bits -->
Source Port      Destination port
Sequence number
Ack number
Length + Flags   Window size
Checksum         Urgent POinter( ungent data to be reached to destination ) 
Optional 40 bytes

Length + Flags
Length(4) + Reserved bits(6) + URG, ACK, PSH, RST, SYN, FIN
URG - urgent pointer is valid
ACK - Ack number is valid
PSH - Request for push
RST - Reset connection
SYN - Synchronize seq number
FIN - Terminate connection

UDP ( 8 bytes )
<-- 16 bits --> <-- 16 bits -->
Source port     Destination port
Length          Checksum      


=== DHCP ===
Uses UDP
Device send broadcast on network.
The router gets it and replies available ip address
THe device takes the ip and sends back a signal
DHCPDiscover - Look for DHCP server
DHCPOffer - Server offers an address
DHCPRequest - Request to take the address
DHCPACK - Server sends ip to the device

=== FTP ===
Used to transfer files.
Not secure. No encrytption of data.
FTPS ( FTP SSL )should be used.
TFTP - Trivial FTP - Uses UDP - Not secure - Dont use over intenet - Use in local transfer



=== Port numbers ===
20 - FTP ( Data )
21 - FTP ( Command )
22 - SSH
23 - Telnet
25 - SMTP
53 - DNS
67,68 - DHCP
69 - TFTP
80 - HTTP
123 - NTP
443 - HTTPS
3389 - RDP
