desc:An army of orcs was spotted not too far from town. We were listening in on some of their communications but we have not been able to find anything containing their battle plans. Maybe they are disguising the messages some how..
so in this question i took much time to get the required packet as they were many packets in HTTP and TCP and after completion of analyzing i gone to ```ICMP```
so there some suspectable data at the end of the each data at the offset "0x22" and i tried to print that data so i used scapy.
```from scapy.all import *
  fil=rdpcap('data.pcap')
  b=''
  for i in fil:
	  if i.haslayer(ICMP):
		  if i[IP].src=="10.136.255.127" and i[IP].dst=='45.58.48.13':
			b+=bytes(i)[34]
open('op.gif','wb').write(b)```
so when we print "b" i found that i got the header of gif file which is ```gif89a```.I was very lucky since my approach is correct and i converted it to a .gif file
and the flag appears.
