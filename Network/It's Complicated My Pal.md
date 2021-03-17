desc: Hey pal, I was sniffing some packets and stumbled upon some weird traffic, no idea what it is though.
Could you take a look at it? It's complicated for me and I can't analyze it by myself.

similar to the bizz question i gone through the packet hierarchy and nothing found except ```ICMP```.so similarly i used scapy to extract 
in the packet ICMP they have given (ascii-dump) of zip

``` from scapy.all import *
f=rdpcap('capture.pcap')
b=''
for i in f:
	if i.haslayer(ICMP) and i[IP].src == '192.168.1.200' and i[IP].dst =='185.245.99.2':
		b+=bytes(i)[42:]
open('ap.zip','wb').write(b)
```
the slicing is the offset that should be considered from
i got the zip which is encrypted and later i used fcrackzip and got the flag
