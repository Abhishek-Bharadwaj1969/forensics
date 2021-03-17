Kevin sent me a file with some hidden message. Help me recover this secret from this bizzare network.
so we were given with a pcap file and we need to extract that
so we can better use ```scapy``` other than manual extraction
step1: get the protocol you required 
        so we can find the whole protocols present in  pcap file using the protocol hierarchy. I tried all the protocols which of no use ecxept ```ICMP```
        so in the ICMP i found some explicit data in the ascii dump of the packet which consists of zip(hex-dump).I then gone to scapy to extract the data
        
        ```from scapy.all import *      
        f=rdpcap('bizz.pcap')
        b=""
        for i in range(len(f)):
	        if f[i].haslayer(ICMP) and len(f[i])>=3524:
		        b+=str(f[i])[142:]
        a=b.decode('hex')
        open("al.zip","wb").write(a)```
  

