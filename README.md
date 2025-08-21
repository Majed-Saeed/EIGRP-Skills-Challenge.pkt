# Packet Tracer - Skills Integration Challenge

## Description
Cisco Packet Tracer project implementing EIGRP for IPv4 and IPv6 with default routes, passive interfaces, and connectivity verification.

## Addressing Table
| Device    | Interface | IPv4 Address     | Subnet Mask       | IPv6 Address/Prefix        |
|-----------|-----------|------------------|-------------------|----------------------------|
| IPv4-Edge | S0/0/0    | 172.31.6.1       | 255.255.255.252   | -                          |
| IPv4-Edge | S0/0/1    | 10.10.8.1        | 255.255.255.252   | -                          |
| IPv4-Edge | S0/1/0    | 209.165.200.226  | 255.255.255.224   | -                          |
| R1        | S0/0/0    | 172.31.6.2       | 255.255.255.252   | -                          |
| R1        | Lo8       | 172.31.0.1       | 255.255.255.128   | -                          |
| R1        | Lo9       | 172.31.0.129     | 255.255.255.128   | -                          |
| R1        | Lo10      | 172.31.1.1       | 255.255.255.128   | -                          |
| R1        | Lo11      | 172.31.1.129     | 255.255.255.128   | -                          |
| R2        | S0/0/1    | 10.10.8.2        | 255.255.255.252   | -                          |
| R2        | Lo1       | 10.10.0.1        | 255.255.255.0     | -                          |
| R2        | Lo2       | 10.10.1.1        | 255.255.255.0     | -                          |
| R2        | Lo3       | 10.10.2.1        | 255.255.254.0     | -                          |
| R2        | Lo4       | 10.10.4.1        | 255.255.252.0     | -                          |
| IPv6-Edge | S0/0/0    | -                | -                 | 2001:DB8:A001:6::1/64      |
| IPv6-Edge | S0/0/1    | -                | -                 | 2001:DB8:A001:7::1/64      |
| IPv6-Edge | S0/1/0    | -                | -                 | 2001:DB8:CAFE:1::2/64      |
| R3        | S0/0/0    | -                | -                 | 2001:DB8:A001:7::2/64      |
| R4        | S0/0/1    | -                | -                 | 2001:DB8:A001:6::2/64      |

## Requirements Implemented
- Configured EIGRP for IPv4 (AS 1) with loopback summarization and passive interfaces.
- Advertised /30 networks using wildcard masks between R1, R2, and IPv4-Edge.
- Default routes propagated to R1 and R2.
- Hello timers on serial interfaces set to 10 seconds.
- Configured EIGRP for IPv6 (AS 1) with router IDs:
  - IPv6-Edge → 1.1.1.1  
  - R3 → 3.3.3.3  
  - R4 → 4.4.4.4  
- Default external route propagated in IPv6 EIGRP.

## Verification
- R1 and R2 can ping the IPv4 server.  
- IPv4 server can ping all loopback addresses on R1 and R2.  
- R3 and R4 can ping the IPv6 server.  
- IPv6 server can ping all loopback addresses on R3 and R4.  

## Topology
(Add a screenshot of your Packet Tracer topology here, e.g. `images/topology.png`)

## Usage
1. Open the `.pkt` file in Cisco Packet Tracer 8.x.  
2. Verify routing tables and connectivity using `ping` and `show ip route` / `show ipv6 route`.  
