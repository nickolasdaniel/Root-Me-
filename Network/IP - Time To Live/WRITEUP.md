# IP - Time To Live
## 15 Points

We have a ```.pcap``` capture file which we are going to open with ```Wireshark```.We have to find the TTL used to reach the destination. The content:
![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Network/IP%20-%20Time%20To%20Live/photos/1.png)


The other TTLs are not responding, these ```13``` and ```51``` are the only ttl which are active. Since the ```TTL 13``` gives us the answer, the password for the challenge is the number of the TTL : ```13```.
