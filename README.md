# Subnet_mask

Addressing and Routing are closely coupled. There are subnetting & supernetting need to be take in account. 

IP addressing provides a logical counterpart to physical network address at link layer.

IP addr is logical in that addr may be changed easily to reflect changes in the logical structure of the network. This is a advantage of flexibility in Network Design.

It is like a trade-off within Addr Strategy in assigning addr space versus the complexity of interpreting.

IP uses an addr mask to show which bits in the addr are host and which are network.

The network prefix can be displayed in 3 formats:

* bit-count, prefered use

* decimal, old style

* hexa, seems like 0x

# cmd

$show ip route

> output is decimal

> R 192.168.1.0 255.255.255.0 [120/2] 192.168.4.1 S1

> C 192.168.2.0 255.255.255.0 is directly connected. E0

$ip netmask-format hexadecimal

> output is hexadecimal

> R 192.168.1.0 0xFFFFF00 [120/2] 192.168.4.1 S1

> C 192.168.2.0 0xFFFFF00 is directly connected. E0

$ip netmask-format bit-count

> output is bit-format

# Natural Mask & Number of Addr

|      mask     |           Addr     |    Usage   |     
----------------|:------------------:|------------|
| 255.255.255.0 |     2e8-2 = 254    |  too less  |
| 255.255.0.0   |   2e16-2 = 65534   | often used |

# Broadcast Addr

|      mask     |     IP Addr   |
----------------|:-------------:|
| 255.255.255.0 | 255.255.255.1 |
| 255.255.0.0   | 255.255.0.1   |

# Advertising Block

192.92.240.0 - 192.92.255.0

192.92.240.0/20
                                               
                                                  /
    External Network -----  192.92.240.0 -------- R --      240.0 ~ 255.0
                           255.255.240.0          \



# Varaible_Length Subnetting

                                                        host
                                                       /
                                                      /
                                                     /
                                                  192.92.243.168 
                                                   / 
                                                  /
                                                 /
                                                /
    ISP                                           ------- 192.92.243.92 ------host
     R  -----  R + hub  ----- 192.92.240.16 ---- R ------- 192.92.243.32 ------ host
     192.92.240.0            255.255.255.252      \      255.255.255.224
     255.255.240.0     |                           \
                       |                            \
                      192.92.240.20                  \ 
                       |                           192.92.243.64
                       R                               \
                       |                                \
                      192.92.245.x                       \ 
                      255.255.255.224                    host
                       |
                       host
