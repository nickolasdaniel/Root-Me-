# CISCO - password
## 15 - Points

We have a config file for a CISCO system and we have to retrieve the ```enable``` password. When we first see the file, we see this:
```
!
! Last configuration change at 13:41:43 CET Mon Jul 8 2013 by admin
! NVRAM config last updated at 11:15:05 CET Thu Jun 13 2013 by admin
!
version 12.2
no service pad
service password-encryption
!
isdn switch-type basic-5ess
!
hostname rmt-paris
!
security passwords min-length 8
no logging console
enable secret 5 $1$p8Y6$MCdRLBzuGlfOs9S.hXOp0.
!
username hub password 7 025017705B3907344E 
username admin privilege 15 password 7 10181A325528130F010D24
username guest password 7 124F163C42340B112F3830
!
!
ip ssh authentication-retries 5
ip ssh version 2
!
interface BRI0/0
 ip address 192.168.1.2 255.255.255.0
 no ip directed-broadcast
 encapsulation ppp
 dialer map ip 192.168.1.1 name hub broadcast 5772222
 dialer-group 1
 isdn switch-type basic-5ess
 ppp authentication chap callin
 no shutdown
!
!
interface GigabitEthernet1/15
 ip address 192.168.2.1 255.255.255.0
 no shutdown
!
router bgp 100
 no synchronization
 bgp log-neighbor-changes
 bgp dampening
 network 192.168.2.0 mask 255.255.255.0
 timers bgp 3 9
 redistribute connected
!
ip classless
ip route 0.0.0.0 0.0.0.0 192.168.1.1
!
!
access-list 101 permit ip any any
dialer-list 1 protocol ip list 101
!
no ip http server
no ip http secure-server
!
line con 0
 password 7 144101205C3B29242A3B3C3927
 session-timeout 600
line vty 0 4
 session-timeout 600
 authorization exec SSH
 transport input ssh

```

After looking a little bit in detail, we can see these lines:

```
username hub password 7 025017705B3907344E 
username admin privilege 15 password 7 10181A325528130F010D24
username guest password 7 124F163C42340B112F3830

```
Cisco systems are using an algorithm a little bit different, often recognised as ```password 7``` as seen above. There's a online tool
which can decrypt our passwords called ```http://www.ifm.net.nz/cookbooks/passwordcracker.html```.

After we put those ```password 7``` from the file, we are given the following outputs:

```
025017705B3907344E = 6sK0_hub
10181A325528130F010D24 = 6sK0_admin
124F163C42340B112F3830 = 6sK0_guest

```

So the only thing's left to do is to try the prefix with the ```enable``` sufix as it follows: ```6sK0_enable```.

Great, it works!


