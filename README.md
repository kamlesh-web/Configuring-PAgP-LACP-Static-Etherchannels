    LACP-Link Aggregation Protocol configurations
    
    Switch>
    Switch>enable
    Switch#
    Switch#configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    Switch(config)#
    Switch(config)#hostname DSW1
    DSW1(config)#
    DSW1(config)#enable secret CCNA
    DSW1(config)#
    DSW1(config)#do show interfaces status
    Port      Name               Status       Vlan       Duplex  Speed Type
    Fa0/1                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/2                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/3                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/4                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/5                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/6                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/7                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/8                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/9                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/10                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/11                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/12                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/13                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/14                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/15                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/16                       connected    1          a-full  a-100 10/100BaseTX
    Fa0/17                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/18                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/19                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/20                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/21                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/22                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/23                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/24                       notconnect   1          auto    auto  10/100BaseTX
    Gig0/1                       notconnect   1          auto    auto  10/100/1000BaseTX
    Gig0/2                       notconnect   1          auto    auto  10/100/1000BaseTX
    
    DSW1(config)#interface range f0/17-24,g0/1-2
    DSW1(config-if-range)#
    DSW1(config-if-range)#description ## Not in use ##
    DSW1(config-if-range)#
    DSW1(config-if-range)#shutdown
    (trancated...)
    DSW1(config-if-range)#
    DSW1(config-if-range)#interface range f0/1-16
    DSW1(config-if-range)#
    DSW1(config-if-range)#no switchport
    DSW1(config-if-range)#
    (trancated...)
    DSW1(config-if-range)#
    DSW1(config-if-range)#channel-group 1 mode active
    DSW1(config-if-range)#
    Creating a port-channel interface Port-channel 1
    (trancated...)
    DSW1(config-if-range)#interface port-channel 1
    DSW1(config-if)#
    DSW1(config-if)#ip address 10.0.0.2 255.255.255.252
    DSW1(config-if)#
    DSW1(config-if)#exit
    DSW1(config)#
    DSW1(config)#do show etherchannel load-balance
    EtherChannel Load-Balancing Configuration:
            src-mac
    
    EtherChannel Load-Balancing Addresses Used Per-Protocol:
    Non-IP: Source MAC address
      IPv4: Source MAC address
      IPv6: Source MAC address
    
    DSW1(config)#port-channel load-balance ?
      dst-ip       Dst IP Addr
      dst-mac      Dst Mac Addr
      src-dst-ip   Src XOR Dst IP Addr
      src-dst-mac  Src XOR Dst Mac Addr
      src-ip       Src IP Addr
      src-mac      Src Mac Addr
    DSW1(config)#port-channel load-balance src-dst-ip
    DSW1(config)#
    DSW1(config)#do write
    Building configuration...
    [OK]
    DSW1(config)#do show etherchannel summary
    Flags:  D - down        P - in port-channel
            I - stand-alone s - suspended
            H - Hot-standby (LACP only)
            R - Layer3      S - Layer2
            U - in use      f - failed to allocate aggregator
            u - unsuitable for bundling
            w - waiting to be aggregated
            d - default port
    
    
    Number of channel-groups in use: 1
    Number of aggregators:           1
    
    Group  Port-channel  Protocol    Ports
    ------+-------------+-----------+----------------------------------------------
    
    1      Po1(RU)           LACP   Fa0/1(P) Fa0/2(P) Fa0/3(P) Fa0/4(P) Fa0/5(P) Fa0/6(P) Fa0/7(P) Fa0/8(P) 
    								Fa0/9(P) Fa0/10(P) Fa0/11(P) Fa0/12(P) Fa0/13(P) Fa0/14(P) Fa0/15(P) Fa0/16(P) 
    								
    								
    ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    
    
    PAgP- Port Aggregation Protocol configurations
    
    Switch>
    Switch>enable
    Switch#
    Switch#configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    Switch(config)#
    Switch(config)#hostname ASW2
    ASW2(config)#
    ASW2(config)#enable secret CCNA
    ASW2(config)#
    ASW2(config)#do show interfaces status
    Port      Name               Status       Vlan       Duplex  Speed Type
    Fa0/1                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/2                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/3                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/4                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/5                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/6                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/7                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/8                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/9                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/10                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/11                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/12                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/13                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/14                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/15                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/16                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/17                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/18                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/19                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/20                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/21                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/22                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/23                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/24                       notconnect   1          auto    auto  10/100BaseTX
    Gig0/1                       notconnect   1          auto    auto  10/100/1000BaseTX
    Gig0/2                       notconnect   1          auto    auto  10/100/1000BaseTX
    
    ASW2(config)#interface range f0/9-24,g0/1-2
    ASW2(config-if-range)#
    ASW2(config-if-range)#description ## Not in use ##
    ASW2(config-if-range)#
    ASW2(config-if-range)#shutdown
    (trancated...)
    ASW2(config-if-range)#
    ASW2(config-if-range)#interface range f0/1-8
    ASW2(config-if-range)#
    ASW2(config-if-range)#no switchport
    (trancated...)
    ASW2(config-if-range)#
    ASW2(config-if-range)#channel-group 1 mode desirable
    (trancated...)
    ASW2(config-if-range)#
    ASW2(config-if-range)#interface port-channel 1
    ASW2(config-if)#
    ASW2(config-if)#ip address 10.0.1.1 255.255.255.252
    ASW2(config-if)#
    ASW2(config-if)#do show etherchannel load-balance
    EtherChannel Load-Balancing Configuration:
            src-mac
    
    EtherChannel Load-Balancing Addresses Used Per-Protocol:
    Non-IP: Source MAC address
      IPv4: Source MAC address
      IPv6: Source MAC address
    
    ASW2(config-if)#port-channel load-balance src-dst-ip
    ASW2(config)#
    ASW2(config)#do show etherchannel summary
    Flags:  D - down        P - in port-channel
            I - stand-alone s - suspended
            H - Hot-standby (LACP only)
            R - Layer3      S - Layer2
            U - in use      f - failed to allocate aggregator
            u - unsuitable for bundling
            w - waiting to be aggregated
            d - default port
    
    
    Number of channel-groups in use: 1
    Number of aggregators:           1
    
    Group  Port-channel  Protocol    Ports
    ------+-------------+-----------+----------------------------------------------
    
    1      Po1(RU)           PAgP   Fa0/1(P) Fa0/2(P) Fa0/3(P) Fa0/4(P) Fa0/5(P) Fa0/6(P) Fa0/7(P) Fa0/8(P) 
    ASW2(config)#
    ASW2(config)#
    ASW2(config)#do write
    Building configuration...
    [OK]
    ASW2(config)#
    
    ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    
    Static EtherChannel configuration
    
    Switch>
    Switch>enable
    Switch#
    Switch#show interfaces status
    Port      Name               Status       Vlan       Duplex  Speed Type
    Fa0/1                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/2                        connected    1          a-full  a-100 10/100BaseTX
    Fa0/3                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/4                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/5                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/6                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/7                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/8                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/9                        notconnect   1          auto    auto  10/100BaseTX
    Fa0/10                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/11                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/12                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/13                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/14                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/15                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/16                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/17                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/18                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/19                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/20                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/21                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/22                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/23                       notconnect   1          auto    auto  10/100BaseTX
    Fa0/24                       notconnect   1          auto    auto  10/100BaseTX
    Gig0/1                       connected    1          a-full  a-100 10/100/1000BaseTX
    Gig0/2                       connected    1          a-full  a-100 10/100/1000BaseTX
    
    Switch#configure terminal
    Enter configuration commands, one per line.  End with CNTL/Z.
    Switch(config)#
    Switch(config)#hostname ASW3
    ASW3(config)#
    ASW3(config)#enable secret CCNA
    ASW3(config)#
    ASW3(config)#interface range f0/3-24
    ASW3(config-if-range)#
    ASW3(config-if-range)#description ## Not in use ##
    ASW3(config-if-range)#
    ASW3(config-if-range)#shutdown
    (trancated...)
    ASW3(config-if-range)#
    ASW3(config-if-range)#interface range f0/1-2,g0/1-2
    ASW3(config-if-range)#
    ASW3(config-if-range)#no switchport
    (trancated...)
    ASW3(config-if-range)#channel-group 1 mode on
    ASW3(config-if-range)#
    Creating a port-channel interface Port-channel 1
    (trancated...)
    ASW3(config-if-range)#
    ASW3(config-if-range)#interface port-channel 1
    ASW3(config-if)#
    ASW3(config-if)#ip address 10.0.2.1 255.255.255.252
    ASW3(config-if)#
    ASW3(config-if)#exit
    ASW3(config)#
    ASW3(config)#do show etherchannel load-balance
    EtherChannel Load-Balancing Configuration:
            src-mac
    
    EtherChannel Load-Balancing Addresses Used Per-Protocol:
    Non-IP: Source MAC address
      IPv4: Source MAC address
      IPv6: Source MAC address
    
    ASW3(config)#port-channel load-balance src-dst-ip
    ASW3(config)#
    ASW3(config)#do show etherchannel summary
    Flags:  D - down        P - in port-channel
            I - stand-alone s - suspended
            H - Hot-standby (LACP only)
            R - Layer3      S - Layer2
            U - in use      f - failed to allocate aggregator
            u - unsuitable for bundling
            w - waiting to be aggregated
            d - default port
    
    
    Number of channel-groups in use: 1
    Number of aggregators:           1
    
    Group  Port-channel  Protocol    Ports
    ------+-------------+-----------+----------------------------------------------
    
    1      Po1(RU)           -      Fa0/1(P) Fa0/2(P) Gig0/1(P) Gig0/2(P) 
    ASW3(config)#
    ASW3(config)#do write
    Building configuration...
    [OK]
    ASW3(config)#
