# Subnet_mask

Addressing and Routing are closely coupled. There are subnetting & supernetting need to be take in account. 

IP addressing provides a logical counterpart to physical network address at link layer.

IP addr is logical in that addr may be changed easily to reflect changes in the logical structure of the network. This is a advantage of flexibility in Network Design.

It is like a trade-off within Addr Strategy in assigning addr space versus the complexity of interpreting.

IP uses an addr mask to show which bits in the addr are host and which are network.

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
 R  -----  R + hub  ----- 192.92.240.5 ---- R ------- 192.92.243.32 ------ host
 192.92.240.0            255.255.255.252      \      255.255.255.224
 255.255.240.0                                 \
                                                \
                                                 \ 
                                                  192.92.243.64
                                                   \
                                                    \
                                                     \ 
                                                       host
