# Linux-networking-commands
A Short networking report of a local PC to understand network commands and some of the fundamentals.

# NETWORK REPORT
hostname: Kali
hostid: 000000
IP address: 10.0.2.20
MAC address: 08:02:27:29:59:1d 
Default Gateway: 10.0.2.2
Listening ports: None.
Trace hops: 30 hops

# Explanation: 
# hostname: a hostname is a human-readable name that is given to our device when its connected to a network. It's for our own convenience as  computer understand numeric data so when a device is connected to a network its mostly acknowledge by its IP address

# hostid: A numeric value assigned to our device. It's essential for software activation or licenses

# IP address: An IP address is a unique four set numeric value given to a device when its connected to network. Every device has a unique numeric value. IP address helps identify which device is connected a network and helps send packets to that specific device
* To know your IP in linux use command: IP addr/ifconfig
  
# MAC address: Every electronic device like pc, mobiles, tv, etc have a MAC address which is basically a hardware number burned into NIC which is a network card and it helps connect device to a network either to wi-fi or ethernet
* To know your mac address use command IP addr and look for "link/ether"

# Default Gateway: A default Gateway helps us connect to a network that is outside of our LAN network. A default gateway which is typically a router can send our packets to a IP address that is not in the same subnet group as our IP address. For instance, if i wish to send something to someone who has a complete different IP address and is not in my LAN network my packet is forwarded to default gateway first.
* To know your default gateway use command: IP route

# Listening ports (netstat):
netstat monitors every connections between your device and the outside world. It shows ports along with IP addresses you can monitor your device by seeing which destination its currently talking to we have listening ports which means its waiting for data while established means an active open connection exists between your computer and the remote address
* Use netstat -a to see every connection and active ports
* netstat -tuna for tcp, udp

# Trace hops: 
It tells how many hops it took for our package to be delivered to the desired destination. A hop is basically when a package moves one router to another to reach the destination. 
* Use traceroute https://example.com
You'll see how many hops it took for our packet to reach the particular website
-----
# ADDITIONALLY COMMANDS.

# Ping: 
An additionally command and an important. Ping tells us if a site is reachable by sending packets ICMP ECHO request and receiving responses which are called ICMP ECHO reply. ICMP ECHO request shouts if the host is there and the host reponse that its here which is called ICMP ECHO request If a host is unreachable that means the host server is down, firewall issue, dns failure, or network problem. 
* Use ping example.com

# nslookup:
nslookup used for dns system it looks for query type like mx for mail servers AAA for IPv4 or IPv6 addresses and NS Records Shows which authoritative Name Servers are responsible for managing the domain's DNS entries.
* Use nslookup example.com and -type=query for specific query e.g MX, AAAA, NS

# arp 
arp is Address Resolution Address protocol which asks for the MAC address of the IP address which its assoicated with. Device A wants to send data to Device B on the local network. Device A knows Device B’s IP address but it needs its physical MAC address to deliver the packet. First, Device A checks its ARP cache (a local temporary table of IP-to-MAC mappings). If the MAC address is already saved there Device A sends the data immediately. If the MAC address is not in the cache ARP sends out a broadcast request to the entire local network: "Who has this IP address? Tell Device A. Device B hears the request, replies directly with its MAC address, and Device A saves that pair into its ARP cache before sending out the data packet.
* Use arp -a


